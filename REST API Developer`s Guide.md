## Analytics > Log&Crash Search > REST API Developer's Guide

HTTP 프로토콜을 사용해서 Log & Crash 수집서버에 로그를 전송할수 있으며, 아래와 같은 JSON형식으로 사용한다.

```
{
	"projectName": "__앱키__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "This log message come from HTTP client.",
	"logSource": "http",
	"logType": "nelo2-log",
	"host": "localhost"
}
```

[기본 파라미터]

```
Log Search를 위한 파라미터들.

projectName: string, 필수
	[in] 앱키.

projectVersion: string, 필수
	[in] 버전. 사용자가 지정할 수 있다. "A~Z, a~z, 0~9,-._" 만을 포함한다.

body: string, 필수
	[in] 로그 메시지. UTF-8을 사용하고 공백이면 안 된다.

logVersion: string, 필수
	[in] 로그 포맷 버전. "v2".

logSource: string, 옵션
	[in] 로그 소스. Log Search에서 필터링을 위해 사용된다. 정의되지 않으면 "http".

logType: string, 옵션
	[in] 로그 타입. Log Search에서 필터링을 위해 사용된다. 정의되지 않으면 "log"

host: string, 옵션
	[in] 로그를 보내는 단말의 주소. 정의되지 않으면 수집서버에서 peer-address를 사용하여 자동으로 채운다.
```

[기타 파라미터]

```
sendTime; string, 옵션
	[in] 단말이 보낸 시간.

logLevel; string, 옵션
	[in] Syslog event용.

UserBinaryData; string, 옵션
	[in] 로그 검색 화면에서 [다운로드|보기] 링크 표시, base64 인코딩된 값을 담아 전송.

UserTxtData; string, 옵션
  [in] 로그 검색 화면에서 [다운로드|보기] 링크 표시, base64 인코딩된 값을 담아 전송.

txt*; string, 옵션
	[in] 필드 이름이 txt로 시작하는 필드(txtMessage, txt_description 등)는 분석(analyzed) 필드로 저장된다. 로그 검색 화면에서 필드 값의 일부 문자열로 검색이 가능하다.
```

[커스텀 필드]

```
커스텀 필드 이름은 "A-Z, a-z"로 시작하고 "A-Z, a-z, 0-9, -, _" 문자를 사용할 수 있다.

위의 기본 파라미터, Crash 파라미터와 이름이 중복되면 안된다.

커스텀 필드의 길이 제한은 2kbyte 로 제한되며, 2kbyte 이상 전송시 txt* prefix 붙여 필드생성 해야된다.
```

[반환값]  
수집 서버에서 다음과 같은 반환을 한다.

```
Content-Type: application/json

{
	"header":{
		"isSuccessful":true,
		"resultCode":0,
		"resultMessage":"Success"
	}
}

isSuccessful: boolean
	[out] 성공시 true, 실패시 false

resultCode: int
	[out] 성공시 0, 실패시 에러 코드

resultMessage: string
	[out] 성공시 "Success", 실패시 에러 메시지
```

> 주의  
> 1. JSON/HTTP로 Log & Crash 수집 서버에 로그 전송시 다음 주소를 사용해야 한다.  
> Log & Crash: api-logncrash.cloud.toast.com  
>
> 전송 방식: POST  
>
> URI: /v2/log  
>
> Content-Type: "application/json"  
> 2. 로그 전송 전에, Log & Crash에 프로젝트를 등록하였는지 확인한다.  
> 3. "logTime"은 Log & Crash 시스템에서 사용한다. 해당 키를 사용시 Log & Crash에서는 무시한다.  
> 4. 키 이름에 공백 문자가 안 들어가도록 주의해야 한다. 예를 들어 "UserID"와 "UserID "은 서로 다른 키로 인식이 된다.  

## 샘플

[curl을 사용하여 정상적으로 로그전송한 경우]

```
//POST 메소드을 사용하여 로그 전송
$ curl -H "content-type:application/json" -XPOST 'http://api-logncrash.cloud.toast.com/v2/log' -d '{
	"projectName": "__앱키__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "this log message come from http client, and it is a simple sample.",
	"logSource": "http",
	"logType": "nelo2-http"
}'
```

[로그 전송이 실패하는 경우]

```
//URL이 잘못된 경우(log -> loggg)
$ curl -v -H 'content-type:application/json' -XPOST "api-logncrash.cloud.toast.com/v2/loggg" -d '{
	"projectName": "__앱키__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "this log message come from http client, and it is a simple sample.",
	"logSource": "http",
	"logType": "nelo2-http"
}'


//잘못된 필드 키를 사용한 경우(_xxx)
$ curl -v -H 'content-type:application/json' -XPOST "api-logncrash.cloud.toast.com/v2/log" -d '{
	"projectName": "__앱키__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "this log message come from http client, and it is a simple sample.",
	"logSource": "http",
	"logType": "nelo2-http",
	"_xxx": "this is a invalid key"
	}'
커스텀 키는 "A~Z, a~z, 0~9, -_"를 포함하고 알파벳으로 시작해야 한다.
커스텀 키는 "A~Z, a~z, 0~9, -_"를 포함하고 알파벳으로 시작해야 한다.
```
