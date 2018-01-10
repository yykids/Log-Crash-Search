## Analytics > Log & Crash Search > Android SDK 사용 가이드

Log & Crash Android SDK는 앱에서 발생한 일반 로그와 크래시 로그를 수집 서버로 보냅니다. Log & Crash Search 에서 전송된 로그를 조회 및 검색이 가능합니다.

### 준비

#### 지원환경
- Android 2.3.3, API Level 10 이상

#### 설치
[Downloads](http://docs.cloud.toast.com/ko/Download/) 페이지에서 Android SDK를 다운로드할 수 있습니다.

#### 파일 구성
- Android SDK는 다음과 같이 구성되어 있습니다.

```
docs/       ; Android SDK 문서
libs/       ; Android SDK 라이브러리
sample/     ; Android SDK 샘플
```

#### AndroidManifest.xml 설정

- 네트워크 상태, 디바이스정보, 통신사, Logcat등의 정보를 가져오기 위하여 권한이 필요합니다.

```
<!-- 로그 전송을 위한 인터넷 접근 권한 (필수) -->
<uses-permission android:name="android.permission.INTERNET" />

<!-- Platform, Carrier등 폰의 정보에 접근하기 위한 권한 (필수) -->
<uses-permission android:name="android.permission.READ_PHONE_STATE" />

<!-- 네트워크 상태에 접근하기 위한 권한 (필수) -->
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

<!-- 네트워크 접속이 안되는 경우 파일로 로그를 저장하기 위한 권한 (옵션) -->
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />

<!-- Logcat에 접근하기 위한 권한 (옵션) -->
<uses-permission android:name="android.permission.READ_LOGS" />

<application
      ......
```

### 샘플 샘플

다음은 SDK 초기화에 사용되는 샘플 코드입니다.

```java
public static final String DEFAULT_APP_KEY = "__app_key__";
public static final String DEFAULT_VERSION = "1.0.0";
public static final String DEFAULT_COLLECTOR_ADDR = "http://api-logncrash.cloud.toast.com";
public static final int DEFAULT_COLLECTOR_PORT = 0;
public static final String DEFAULT_LOG_SOURCE = "logncrash-logSource";
public static final String DEFAULT_LOG_TYPE = "logncrash-logType";

public static boolean initialize(Application application, String collectorAddr, int collectorPort, String appKey, String version, String userId);

public static boolean initialize(Application application, String collectorAddr, int collectorPort, String appKey, String version, boolean syncStart);
```
1. application : getApplication() 반환값
2. collectorAddr : 수집 서버 주소
3. collectorPort : http 80, https 443
4. appKey : 앱 키
5. version : 앱 버전
6. userId : 사용자 아이디
7. syncStart

	a. true : startSendThread가 호출되기 전까지 로그 전송을 하지 않습니다. 단 Crash가 발생한 경우 ThreadLock을 해제하고 로그를 전송합니다.
	
	b. false : initialize 이후 로그를 전송합니다. 설정하지 않으면 false로 동작합니다.
	
다음은 SendThread 잠금 상태를 해제하는 샘플 코드입니다.

```java
public static void startSendThread();
```
1. initialize의 syncStart가 true인 경우, 해당 함수 호출 이후부터 로그를 전송합니다.
	
다음은 로그 전송 샘플 코드입니다.

```java
public static void fatal(String message, Throwable t)
public static void error(String message, Throwable t)
public static void warn(String message, Throwable t)
public static void info(String message, Throwable t)
public static void debug(String message, Throwable t)
public static void crash(String message, Throwable t)

public static void fatal(String message)
public static void error(String message)
public static void warn(String message)
public static void info(String message)
public static void debug(String message)
```
1. message : 로그 메시지. null이나 ""를 쓰면 기본 메시지가 전송됩니다.
2. Throwable t : 수집된 에러를 같이 전송합니다. null을 사용할 수 있습니다.

다음은 커스텀 필드를 지정하는 샘플 코드입니다.

```java
public static void addCustomField(String key, String value)
public static void removeCustomField(String key)
public static void clearCustomFields()
```

1. 커스텀 필드 추가, 삭제 기능을 제공합니다.
2. SDK에서 미리 사용하고 있는 필드는 커스텀 필드로 사용할 수 없습니다.

다음은 SDK에서 미리 사용하고 있는 필드 정보입니다.

```
"projectName", "projectVersion", "body", "logSource", "logType",
"host", "sendTime", "logLevel", "DmpData", "Platform", "NeloSDK", 
"Exception", "Location", "Cause", "SessionID", "UserID", "Carrier", 
"CountyCode", "DeviceModel", "Locale", "NetworkType", "Rooted", 
"LogcatMain", "LogcatRadio", "LogcatEvents"
```

다음은 초기화 이후 SDK가 캐싱하고 있는 정보를 반환하는 샘플 코드입니다.

```java
public static String getAppKey()
public static String getVersion()
public static String getCollectorAddr()
public static int getCollectorPort()
```
1. 앱키, 버전, 수집서버 주소, 수집서버 포트를 반환합니다.

다음은 로그 소스를 설정하는 샘플 코드입니다.

```java
public static String getLogSource()
public static void setLogSource(String logSource)
```

다음은 로그 타입을 설정하는 샘플 코드입니다.

```java
public static String getLogType()
public static void setLogType(String logType)
```
다음은 중복로그 제거 설정 샘플 코드입니다. 

```java
public static void setDuplicate(bool enable)
```
1. body, logLevel, logType, logSource가 같은 경우 중복로그로 인식합니다.
2. enable : true이 경우 중복로그 제거 활성화