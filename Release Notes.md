## Analytics > Log&Crash Search > Release Notes

### 2016.10.20
#### 기능 개선/변경
* 기기의 고유 ID 값인 DeviceID 수집
    * 신규 SDK을 통한 Crash Log 전송시 DeviceID가 수집되어 Console > Log&Crash Search > Crashes > 앱 크래시 지표 화면에서
      DeviceID 기준으로 지표 확인이 가능합니다.
* [SDK] 로그 전송이 안되는 경우 파일로 저장 후 이후 정상 통신이 되는 경우 로그 파일 전송하도록 기능 변경됨.
* [Console] 앱 크래시 지표 화면 > '세션','사용자수' 타이틀 '실행 수' '크래시를 겪은 사용자'로 변경됨.

### 2016.09.29
#### 기능 개선/변경
* 알람 임계치 설정 및 http Callback 기능 추가
    * 알람 임계 값 비교 연산자 지원(>,>=,=,<=,<)
    * n 시간전 비교 이상/이하 기능 추가
    * Snooze 기능 추가
* Log Search 화면에서 다운로드 가능한 UserTxtData 필드 추가
    * "UserTxtData" 필드는 Log Search 화면에서 [다운로드|보기] 표시 하여 필드 내용을 바로 확인이 가능

#### 버그 수정
* [SDK] Exception이 발생한 경우 , 로그 전송 객체를 초기화 하지 못하여 반복적으로 초기화를 재시도 하던 버그 수정
    * 수정된 SDK : logback , log4j, log4j2
* [SDK] init 함수에 UserID를 세팅하면 로그에 값이 정상적으로 추가되지 않던 버그 수정
    * 수정된 SDK : iOS

### 2016.09.12
#### 버그 수정
* [SDK] Carrier와 Carrier 값이 null이 return되는 케이스에 대한 예외처리 코드 추가
    * 수정된 SDK : Unity(v.2.3.4)

### 2016.08.22
#### 기능 개선/변경
* Custom Field Default 옵션 및 길이 제한 변경
    * Custom 필드 생성시 analyzed(분석여부) false 로 변경
    * 전송 가능한 로그 길이 128byte -> 2Kbyte 변경
    * 2Kbyte 이상의 로그 전송이 필요한 경우 Field 명에 txt prefix 지정하여 Custom field 생성

    ```
    txt*; string, 옵션 [in] 필드 이름이 txt로 시작하는 필드(txt_description 등)는 분석(analyzed) 필드로 저장
    
    로그 검색 화면에서 필드 값의 일부 문자열로 검색이 가능
    ```

### 2016.08.18
#### 기능 개선/변경
* Log 전송 ON / OFF 기능 추가
    * Log&Crash Search 로 전송되는 로그(일반로그/크래시로그/세션로그)에 대해 사용자가 콘솔에서
      On/Off 설정, 수집여부를 결정할수 있습니다.
    * 수집되지 않은 로그는 화면에 노출되지 않고, API 및 Storage 요금에 포함되지 않습니다.
    * Log on/off 기능 추가로 SDK 업데이트 되었습니다.
        * 대상 SDK(v.2.3.0) : Unity, Android , Windows, iOS

* [API] UserBinaryData 필드 추가
    * 로그 파일이나 바이너리 파일을 위 필드로 전송시 로그 검색 화면에 다운로드 가능

#### 버그 수정
* [Console] Crash 상세 페이지 로딩 속도 문제 수정


### 2016.08.04
#### 기능 개선/변경
* [SDK][Unity] 2.2.6 업데이트
    * SaveToFile 저장 포맷 변경
    * Regular Expression, JSON 라이브러리를 사용하여 변환하도록 수정
    * 파일 최대 저장 개수 100개 제한
    * 중복 제거 큐 100개 제한

#### 버그 수정
* [API] 특정 필드에 json array나 object를 전송한 경우 string으로 변환 되는 현상 수정
