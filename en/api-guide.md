## Analytics > Log & Crash Search > API Guide

Logs can be sent to the Log & Crash Collector server by using HTTP protocol, in the JSON format as below:

```
{
	"projectName": "__Appkey__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "This log message come from HTTP client.",
	"logSource": "http",
	"logType": "nelo2-log",
	"host": "localhost"
}
```

[Default Parameters]

```
Parameters for Log Search

projectName: string, required
	[in] Appkey

projectVersion: string, required
	[in] Verwion. User can specify: include "A~Z, a~z, 0~9,-._" only.

body: string, optional
	[in] Log messages.

logVersion: string, required
	[in] Log format version. "v2".

logSource: string, optional
	[in] Log source. Used to filter at Log Search. "http", if not defined.

logType: string, optional
	[in] Log type. Used to filter at Log Search. "log", if not defined.

host: string, optional
	[in] Address of the device sending logs: if not defined, fill automatically with peer-address of the collector server.
```

[Other Parameters]

```
sendTime; string, optional
	[in] Sending time of a device. Enter in Unix Timestamp

logLevel; string, optional
	[in] For Syslog events.

UserBinaryData; string, optional
	[in] Display [Download|Show] link on the log search screen, and send with values encoded with base64.

UserTxtData; string, optional
  [in] Display [Download|Show] link on the log search screen, and send with values encoded with base64.

txt*; string, optional
	[in] Save fields starting with txt (such as txtMessage and txt description) in analyzed fields. Search is available with a part of character strings of the field value on the log search screen.

long*; long, optional
    [in] Save fields starting with long (such as longElapsedTime and long elapsed time) in the long-type fields. Search of long-type range is available on the log search screen.

double*; double, optional
    [in] Save fields starting with double (such as doubleAvgScore and double avg score) in the double-type fields. Search of double-type range is available on the log search screen.
```

[Custom Fields]

```
A custom field can be named with "A-Z, a-z, 0-9, -, _", starting with "A-Z, a-z".

Cannot be redundantly named with default parameters of the above or crash parameters.

The length of a custom field is limited to 2kbytes, and if it exceeds 2kbytes, the field must be created with txt* prefix.
```

[Return Value]
Return as below in the collector server:

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
	[out] true if successful, false if failed

resultCode: int
	[out] 0 if successful, error code if failed

resultMessage: string
	[out] "Success" if successful, error message if failed
```

[Bulk Delivery]
For bulk delivery, send in the JSON array format to the collector server.

```
[
    {
        "projectName": "__Appkey__",
        "projectVersion": "1.0.0",
        "logVersion": "v2",
        "body": "This log message come from HTTP client. (1/2)",
        "logSource": "http",
        "logType": "nelo2-log",
        "host": "localhost"
    },
    {
        "projectName": "__Appkey__",
        "projectVersion": "1.0.0",
        "logVersion": "v2",
        "body": "This log message come from HTTP client. (2/2)",
        "logSource": "http",
        "logType": "nelo2-log",
        "host": "localhost"
    }
]
```

* Note
	* In the web, logs are arrayed in the order of receiving time. However, for bulk delivery, the receiving time is considered the same for all logs, and the user’s sending time cannot be maintained.
	* To maintain the order of sending time of logs for bulk delivery, add the IncBulkIndex field to each log and specify the integer value before delivery. Then, the server shall show them in the descending order based on such value.  

```
[
    {
        "projectName": "__Appkey__",
        "projectVersion": "1.0.0",
        "logVersion": "v2",
        "body": "first message",
        "logSource": "http",
        "logType": "nelo2-log",
        "host": "localhost",
        "lncBulkIndex":1
    },
    {
        "projectName": "__Appkey__",
        "projectVersion": "1.0.0",
        "logVersion": "v2",
        "body": "second message",
        "logSource": "http",
        "logType": "nelo2-log",
        "host": "localhost",
        "lncBulkIndex":2
    }
]
```
	* For deliveries like the above, the server shows in the order of second message -> first message.

In the collector server, each result value is returned in the JSON array format in the order of delivery.

```
Content-Type: application/json

{
    "header":{
        "isSuccessful":true,
        "resultCode":0,
        "resultMessage":"Success"
    },
    "body":{
        "data":{
            "total":5,
            "errors":2,
            "resultList":[
                {"isSuccessful":true, "resultMessage":"Success"},
                {"isSuccessful":true, "resultMessage":"Success"},
                {"isSuccessful":false, "resultMessage":"LogVersion Mismatch: v1, /v2/log"},
                {"isSuccessful":false, "resultMessage":"The project(invalidProject) is not registered"},
                {"isSuccessful":true, "resultMessage":"Success"}
            ]}
        }
    }
}

total: int
    [out] Total number of delivered logs

errors: int
    [out] Number of errors in delivered logs

resultList: array
    [out] Result value of each delivered log
```

> Caution
> 1. To send logs in JSON/HTTP to the Log & Crash Collector server, use the address as follows:
> Log & Crash: api-logncrash.cloud.toast.com
>
> Method of Delivery: POST
>
> URI: /v2/log
>
> Content-Type: "application/json"
> 2. Check, before log delivery, if a project has been registered to Log & Crash Search.
> 3. Field name "logTime" is occupied by Log & Crash Search system. User cannot set "logTime" field.
> 4. Keep note that a key name has no whitespace character. For example, “UserID” and “UserID ” are considered two different keys.

## Samples

[Normal log delivery by using curl]

```
//Deliver logs by using POST method
$ curl -H "content-type:application/json" -XPOST 'https://api-logncrash.cloud.toast.com/v2/log' -d '{
	"projectName": "__Appkey__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "this log message come from http client, and it is a simple sample.",
	"logSource": "http",
	"logType": "nelo2-http"
}'
```

[Failed log delivery]

```
//When URL is incorrect (log -> loggg)
$ curl -v -H 'content-type:application/json' -XPOST "api-logncrash.cloud.toast.com/v2/loggg" -d '{
	"projectName": "__Appkey__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "this log message come from http client, and it is a simple sample.",
	"logSource": "http",
	"logType": "nelo2-http"
}'


//When a wrong field key (_xxx) is used
$ curl -v -H 'content-type:application/json' -XPOST "api-logncrash.cloud.toast.com/v2/log" -d '{
	"projectName": "__Appkey__",
	"projectVersion": "1.0.0",
	"logVersion": "v2",
	"body": "this log message come from http client, and it is a simple sample.",
	"logSource": "http",
	"logType": "nelo2-http",
	"_xxx": "this is a invalid key"
	}'
The custom key must include "A~Z, a~z, 0~9, -_" and start with an alphabet.
The custom key must include "A~Z, a~z, 0~9, -_" and start with an alphabet.
```

[Bulk log delivery using curl]

```
//Deliver logs by using POST method
$ curl -H "content-type:application/json" -XPOST 'https://api-logncrash.cloud.toast.com/v2/log' -d '[
    {
        "projectName": "__Appkey__",
        "projectVersion": "1.0.0",
        "logVersion": "v2",
        "body": "This log message come from HTTP client, and it is a simple bulk sample. (1/2)",
        "logSource": "http",
        "logType": "nelo2-log"
    },
    {
        "projectName": "__Appkey__",
        "projectVersion": "1.0.0",
        "logVersion": "v2",
        "body": "This log message come from HTTP client, and it is a simple bulk sample. (2/2)",
        "logSource": "http",
        "logType": "nelo2-log"
    }
]'
```
