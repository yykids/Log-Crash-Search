## Analytics > Log & Crash Search > Logback SDK 사용 가이드

Log & Crash Logback SDK는 Log & Crash Search 수집 서버에 로그를 보내는 기능을 제공합니다.
Log & Crash Log4back SDK 특·장점은 다음과 같습니다.

- 로그를 수집 서버로 보냅니다.
- Log & Crash Search 에서 전송된 로그를 조회 및 검색이 가능합니다.
- 멀티 쓰레딩 환경에서 동작합니다.

## 지원 환경

- Logback 1.X+

## 다운로드

[TOAST Document](http://docs.toast.com/ko/Download/)에서 Logback SDK를 받을 수 있습니다.

```
[DOCUMENTS] > [Download] > [Analytics > Log & Crash Search] > [Logback SDK] 클릭
```

## 설치

### 구성

Logback SDK는 다음과 같이 구성되어 있습니다.

```
docs/       ; Logback SDK 문서
lib/        ; Logback 라이브러리
sample/
```

## Maven Dependency 추가

1.pom.xml에 dependency를 추가합니다.  

```
<dependency>
    <groupId>com.toast.java.logncrash.logback</groupId>
    <artifactId>logncrash-java-sdk3</artifactId>
    <version>3.0.2</version>
</dependency>
```

## Logger 설정

1.Appender 설정과 구성을 위해서 logback.xml을 작성합니다.  

- logback의 AsyncAppender를 기본으로 사용하여 로그를 비동기로 수집하여 로그 수집 서버로 전송합니다.

```xml
<property name="ACTIVE_PROFILE" value="${spring.profiles.active}"/>
<property name="APP_KEY" value="${appKey}"/>
<property name="INCLUDE_CALLER_DATA" value="false"/>
<property name="QUEUE_SIZE" value="2048"/>
<property name="NEVER_BLOCK" value="true"/>
<property name="MAX_FLUSH_TIME" value="60000"/>

<appender name="user-logger" class="ch.qos.logback.classic.AsyncAppender">
    <filter class="ch.qos.logback.classic.filter.ThresholdFilter">
        <level>INFO</level>
    </filter>
    <param name="includeCallerData" value="${INCLUDE_CALLER_DATA}"/>
    <param name="queueSize" value="${QUEUE_SIZE}"/>
    <param name="neverBlock" value="${NEVER_BLOCK}"/>
    <param name="maxFlushTime" value="${MAX_FLUSH_TIME}"/>
    <appender name="logNCrashHttp" class="com.toast.java.logncrash.logback.LogNCrashHttpAppender">
        <param name="logSource" value="${ACTIVE_PROFILE}"/>
        <param name="appKey" value="${APP_KEY}"/>
        <param name="category" value="${서비스명}"/>
        <param name="logType" value="logType"/>
    </appender>
</appender>

<logger name="user-logger" additivity="false">
    <appender-ref ref="user-logger"/>
</logger>
```


### Property 설명

| 키 | 설명 |
|---|---|
| ACTIVE_PROFILE | alpha, beta, real 등 실행 되는 환경 설정 정보입니다.<br>Spring Profile을 사용하는 경우, ${spring.profiles.active} 사용합니다. |
| APP_KEY | logncrah 콘솔에서 활성화한 projectKey입니다. |
| INCLUDE_CALLER_DATA | 로그에 상세 정보(class명, 줄번호 등) 추가 여부 결정합니다.<br>true로 설정 시, 성증 저하를 발생시킬 수 있습니다.|
| QUEUE_SIZE | blocking queue의 최대 수용 갯수, 기본값은 256입니다. |
| NEVER_BLOCK | false로 설정한 경우 큐가 가득찬 상황에서 appender는 메세지 유실을 방지하기 위해 application을 block 합니다. <br>true로 설정된 경우 application을 멈추지 않기 위해 메세지를 버립니다.|
| MAX_FLUSH_TIME | LoggerContext이 정지하면 AsyncAppender의 stop 메소드는 작업 스레드가 timeout 될때까지 대기<br> maxFlushTime를 사용하면, timeout 시간을 밀리초로 설정할 수 있습니다.<br>해당 시간안에 처리하지 못한 이벤트는 삭제됩니다. |

### LogNCrashHttpAppender Param 설명

| 키 | 설명 |
|---|---|
| logType | ACTIVE_PROFILE의 환경 설정 정보가 기입되는 항목입니다. (alpha, bata, real) |
| logSource | APP_KEY의 logncrah의 appkey가 기입되는 항목입니다.|
| appKey | log가 어떤 type인지 설명하는 항목입니다. |
| cetetory | logType의 어떤 category인지 설명하는 항목입니다. |

## 샘플

```java
@Slf4j
@ResponseBody
public class GlobalExceptionHandler {
    private static final Logger USER_LOG = LoggerFactory.getLogger("user-logger");
 
   
    public JsonNode handlerException(Exception exception, HttpServletRequest request) throws IOException {
		...
        MDC.setContextMap(cabAuditBean.convertMap());                               
        // StandardCharsets.UTF_8은 서비스 환경에 맞게 변경하면 된다.
        USER_LOG.error("exception body", exception);               
        MDC.clear();
		...         
        return getJson(exception);
    }
}
```
