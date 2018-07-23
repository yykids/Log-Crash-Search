## Analytics > Log & Crash Search > Console Guide

Log & Crash Search는 다음과 같은 순서로 사용합니다.

- 서비스 활성화  
Console에서 프로젝트를 선택한 후, Log & Crash 을 활성화 시킵니다.
- 로그 전송  
Log & Crash Search SDK를 통해서 로그 전송을 시작합니다.
- 로그 확인  
로그 전송을 마친 후에는 Log Search 혹은 App Crash Search 화면에서 차트나 질의 등 다양한 방식으로 로그를 살펴볼 수 있습니다.

## 프로젝트 선택

Console에 접속하여 왼쪽 메뉴를 이용하여 조직(Organization)과 프로젝트(Project)를 선택합니다. 기존에 조직이나 프로젝트가 존재하지 않는 경우, 신규로 생성합니다.

```
왼쪽 메뉴에서 [ORGANIZATION]과 [PROJECT]를 순차적으로 선택
```

## 서비스 활성화

프로젝트(Project)를 선택한 상태에서 화면 상단의 [서비스] 버튼을 클릭하고 Analytics 분류의 Log & Crash Search를 찾아서 활성화합니다. Log & Crash Search를 클릭하여 활성화하면 초록색이 켜집니다.  

```
화면 상단의 [서비스] 버튼 클릭
```

> [참고]  
> 서비스를 활성화한 이후에는 약 5분 이후부터 전송 가능합니다.

![[그림 1 그림 1 서비스 버튼 클릭]](http://static.toastoven.net/prod_logncrash/console_1.png)
<center>[그림 1 서비스 버튼 클릭]</center>

![[그림 1-1 Log & Crash Search 서비스 활성화]](http://static.toastoven.net/prod_logncrash/console_1-1.png)
<center>[그림 1-1 Log & Crash Search 서비스 활성화]</center>

Log & Crash Search 가 활성화되면 왼쪽 메뉴에 Analytics > Log & Crash Search 메뉴가 노출되고 Appkey가 생성됩니다.

## Appkey 확인

로그 전송을 위해 Appkey를 확인할 필요가 있습니다. 왼쪽 메뉴에서 Log & Crash Search를 찾아서 선택하면 Log & Crash Search 콘솔에 접근할 수 있습니다. 콘솔 화면 상단에 "URL & Appkey" 버튼을 클릭하면 Log & Crash Search용 Appkey를 확인할 수 있습니다. 

```
왼쪽 메뉴에서 [Analytics] > [Log & Crash Search] > [Log Search] 클릭
화면 상단의 [URL & Appkey] 버튼을 클릭하여 Appkey 확인
```

![[그림 2 Appkey 확인]](http://static.toastoven.net/prod_logncrash/console_2.png)
<center>[그림 2 Appkey 확인]</center>

## 로그 전송

로그 전송을 위해서는 Log & Crash Search SDK가 필요합니다. SDK는 [TOAST 개발자센터](http://toast.com/developer_center)의 화면의 [서비스] 버튼을 클릭하고 [Downloads] 메뉴를 클릭하면 다운로드 페이지가 노출됩니다. [Analytics > Log & Crash Search] 영역에서 Log & Crash Search SDK 목록을 확인할 수 있습니다. [링크](http://docs.toast.com/en/Download/#analytics-log-crash-search). 화면 왼쪽 상단의 [서비스] 버튼을 클릭하고 [Analytics] > [Log & Crash Search]를 클릭하여 각 플랫폼별 SDK의 사용 가이드를 참고하실 수 있습니다. SDK 사용 가이드를 참고하여 로그를 전송해 주십시오.  

```
SDK 다운로드: [개발자센터] > [설명서] > [Downloads] > [Analytics > Log & Crash Search] 영역의 SDK 다운로드
SDK 사용 가이드: [개발자센터] > [설명서] > [Analytics] > [Log & Crash Search]에서 사용하려는 SDK의 사용 가이드 참고
```

> [참고]  
> 로그량이 적은 경우에는 약 5분 후, 로그 전송 결과가 반영됩니다.

## 로그 검색

이제 전송한 로그를 Log Search 기능을 이용하여 검색해보겠습니다.

```
콘솔 화면 왼쪽 메뉴의 [Analytics] > [Log & Crash Search] > [Log Search] 클릭
```

[Log Search]로 들어가면 기본적으로 24시간 동안의 로그량이 그래프와 상세 내용으로 나옵니다.

![[그림 3 Log Search 진입]](http://static.toastoven.net/prod_logncrash/console_3.png)
<center>[그림 3 Log Search 진입]</center>

![[그림 3-1 Log Search 화면]](http://static.toastoven.net/prod_logncrash/console_3-1.png)
<center>[그림 3 Log Search 화면]</center>

[Log Search] 화면의 세부 항목을 살펴보겠습니다.

![[그림 4 Log Search 상세 내용]](http://static.toastoven.net/prod_analytics/log_4.jpg)
<center>[그림 4 Log Search 상세 내용]</center>

| 항목 | 설명 |
|---|---|
| 검색 쿼리 입력 | 쿼리 필드 검색은 Lucene 문법을 사용할 수 있습니다. <br/> (참고: http://lucene.apache.org/core/2_9_4/queryparsersyntax.html)|
| 검색 대상 기간 | 검색 쿼리의 기간 조건을 설정할 수 있습니다. |
| 로그 검색 결과 > 차트 | 로그 검색 결과를 막대 그래프로 출력하며, 클릭하면 오른쪽 단위(ex: 1Bar=1hour)에 맞는 기간을 기준으로 출력합니다. |
| 필드 검색 조건 | - host: 호스트 이름이나 IP 주소로 구분<br/> - logLevel: 로그 레벨로 구분 (FATAL / ERROR / WARN / INFO / DEBUG)<br/> - logSource: 사용자가 설정한 로그 소스로 구분<br/> - logType: 사용자가 설정한 프로젝트 이름으로 구분<br/> - projectVersion: 사용자가 설정한 프로젝트 버전으로 구분<br/><br/> - Show all fields를 클릭하여 다른 필드를 검색 조건으로 사용할 수 있습니다. |
| 로그 검색 결과 > 로그 레코드 | 검색한 로그의 자세한 내용이 출력되는 부분입니다. 출력된 로그의 각 항목은 클릭하여 검색 쿼리를 변경할 수 있습니다. |

사용자가 설정한 검색 조건은 검색 쿼리 입력창에 반영이 되는데, 이 쿼리를 저장할 수도 있고([쿼리 저장]), 기존에 저장되어 있는 쿼리를 이용해서 검색할 수도([저장 쿼리 선택]) 있습니다.

## 앱 크래시 조회

Android, iOS 단말의 크래시 정보는 App Crash Search에서 볼 수 있습니다.

```
[Analytics] > [Log & Crash Search] > [App Crash Search] 클릭
```

### 이슈조회

![[그림 5-1 이슈조회]](http://static.toastoven.net/prod_analytics/log_5.jpg)
<center>[그림 5-1 이슈조회]</center>

![[그림 5-2 Handled 이슈조회]](http://static.toastoven.net/prod_analytics/log_18.jpg)
<center>[그림 5-2 Handled 이슈조회]</center>

|항목|	설명|
|---|---|
|에러타입| 시스템에서 발생 시키는 Crash와 Exception 블럭에서 사용자가 발생시키는 Handled로 분류 됩니다.|
|필터 조건|	상태 – 크래시 이슈 처리 상태 <br/> 최근 – 최근 N일간 수집된 크래시 로그 조회 필터 <br/> 앱 버전 – 앱 버전 <br/> 태그 – 태그 <br/> 최소 발생수 – 크래시 발생 최소 N건 이상인 크래시 조회 필터 <br/> 예외종류 – 예외 종류별 최근 필터 <br/> 위치 – 크래시 발생 지점별 조회 필터 |
|차트| 크래시 발생 건수를 타임라인 차트로 표시 합니다.|
|이슈목록|이슈 목록을 출력합니다. 우측 상단 리스트 박스를 이용해 정렬 순서를 변경할 수 있으며, 목록 좌측 체크박스를 통해 이슈 상태를 변경할 수 있습니다.|

목록에서 이슈를 클릭하면 해당 이슈에 대한 상세 정보를 보여줍니다.

![[그림 6 상세 정보]](http://static.toastoven.net/prod_analytics/log_6.jpg)
<center>[그림 6 상세 정보]</center>

|항목|	설명|
|---|---|
|상태|	이슈 상태를 미해결, 해결, 재등록, 완료 등의 상태로 설정할 수 있습니다|
|이슈 트래커 설정|	GitHub, GitLab 등 외부 이슈 트래커를 설정하여 해당 이슈를 외부 이슈 트래커에 등록할 수 있습니다|
|태그|	태그를 추가하거나 추가된 태그를 변경,삭제할 수 있습니다|
|ETC - 검색 페이지에서 보기|	클릭하면 로그 검색 페이지로 이동합니다|
|히스토리 그래프| 이슈 발생 건수를 타임라인 차트와 월드맵으로 표시해 줍니다|
|매트릭스 정보| 네트워크, OS버전, 디바이스, 통신사, 국가 정보를 표시해 줍니다|
|스텍 트레이스|	크래시가 발생한 예외 종류, 예외 원인 및 스택 트레이스 정보를 보여 줍니다|
|에러 인스턴스|	에러 인스턴스 목록을 보여 줍니다|
|사용자| 이슈를 발생시킨 사용자 목록을 보여 줍니다|
|코멘트|	해당 이슈에 대해 코멘트를 작성할 수 있으며 프로젝트 구성원들이 작성한 코멘트 목록을 보여 줍니다|
|히스토리|	해당 이슈에 대한 관리 이력(상태 변경, 태그 추가, 코멘트 작성 등)을 타임라인으로 보여 줍니다|

### 실시간 모니터링

![[그림 7 실시간 모니터링]](http://static.toastoven.net/prod_analytics/log_7.jpg)
<center>[그림 7 실시간 모니터링]</center>

약 5분 동안의 실시간 앱 크래시 발생을 모니터링 합니다.

### 트렌드

![[그림 8 트렌드 항목 내용]](http://static.toastoven.net/prod_analytics/log_8.jpg)
<center>[그림 8 트렌드 항목 내용]</center>

|항목|	설명|
|---|---|
|시간 조건| 통계 시간 조건을 설정할 수 있습니다. <br/> (7일, 2주, 30일)|
|트렌드 그래프| 다양한 트렌드 그래프를 볼 수 있습니다. <br/> - 크래시 카운트 <br/> - 사용자 수 <br/> - 모든 에러 통계 <br/> - 미해결 에러 통계 <br/> - 앱 버전별 이슈 통계 <br/> - OS 버전별 이슈 통계 <br/> - 디바이스별 이슈 통계 <br/> - 국가별 이슈 통계|

### 앱 크래시 지표

|항목|	설명|
|---|---|
|앱 크래시 지표|	세션/크래시파일/발생률(%)/이전 기간 크래시/증가율(%) 정보를 제공합니다.|
|앱 크래시 추이|	사용자가 지정한 기난 내 발생수 정보를 제공합니다.|
|크래시 맵| 사용자가 지정한 기간 내 발생 크래시 수를 지도상에 표시해 줍니다.|

세분화 지정을 통해 통계자료를 확인합니다.

1. 앱 크래시 지표 링크를 클릭하여 앱 크래시 추이 화면으로 전환할 수 있습니다.
2. 플랫폼(iOS, Android, Windows)을 선택하여 필터링 검색할 수 있습니다.
3. 검색 기간과 검색 건수를 조정할 수 있습니다.
4. 버전별 결과를 테이블로 확인할 수 있습니다.

![[그림 9 앱 크래시 지표 내용]](http://static.toastoven.net/prod_analytics/log_11.jpg)
<center>[그림 9 앱 크래시 지표 내용]</center>

![[그림 9-1 크래시 맵 내용]](http://static.toastoven.net/prod_analytics/crashmap_en.png)
<center>[그림 9-1 크래시 맵 내용]</center>

### 크래시 사용자

사용자별 크래시 발생 정보를 제공합니다.

1. SDK 에서 user_id를 설정할 경우 사용 가능하며 저장하지 않을 경우 모든 사용자는 '-'로 표시 됩니다.
2. 유니크한 사용자는 사용자 아이디와 디바이스명의 조합입니다. 즉, 사용자 아이디가 같아도 디바이스가 다르면 다른 사용자로 집계 됩니다.

![[그림 9-2 크래시 사용자 내용]](http://static.toastoven.net/prod_analytics/crashuser_en.png)
<center>[그림 9-2 크래시 사용자 내용]</center>

|항목|	설명|
|---|---|
|에러 타입|	시스템에서 발생 시키는 Crash 통계와 Exception 블럭에서 사용자가 발생시키는 Handled로 분류됩니다.|
|사용자|	SDK에서 user_id로 지정한 사용자 아이디를 검색 조건으로 설정할 수 있습니다.|
|디바이스| 디바이스명을 검색 조건으로 설정할 수 있습니다.|
|시간 조건| 사용자별 크래시 조회 시간 조건을 설정할 수 있습니다.|
|앱 버전| 앱 버전별로 필터링 합니다.|

### 이슈통계

![[그림 10-1 이슈통계]](http://static.toastoven.net/prod_analytics/log_9.jpg)
<center>[그림 10-1 이슈통계]</center>

![[그림 10-2 Handled 이슈통계]](http://static.toastoven.net/prod_analytics/log_19.jpg)
<center>[그림 10-2 Handled 이슈통계]</center>

|항목|	설명|
|---|---|
|에러 타입|	시스템에서 발생 시키는 Crash 통계와 Exception 블럭에서 사용자가 발생시키는 Handled 통계로 분류됩니다|
|시간 조건|	통계 시간 조건을 설정할 수 있습니다|
|앱 버전|	앱 버전별로 필터링 합니다|
|크래시별 발생 빈도 파이 그래프|	크래시별 발생 빈도를 보여줍니다|
|크래시별 발생 빈도 순위 테이블|	크래시별 발생 빈도 순위를 보여줍니다|

## 알람

로그 및 크래시에 대한 알람 설정 및 알람 발송 이력을 확인할 수 있습니다.

```
[Analytics] > [Log & Crash Search] > [Alarms] 클릭
```

### 로그 알람 설정

로그 알람에 대한 모든 기능을 수행할 수 있는 페이지입니다.

- 알람은 발생수에 따른 알람과, 로그의 증감률에 따른 알람으로 구분됩니다.
- 알람 수신을 원하는 로그유형(Lucene 쿼리)을 등록하고 해당 로그가 발생하면 조건에 따라 알람을 발송합니다.
- [발생수], [증감률] 두 가지 유형의 알람이 있습니다.
- [알람 추가] 버튼을 누르면 알람을 등록할 수 있습니다.

### 로그 알람 조회
- 구체적인 알람 내용을 보거나 수정할 수 있습니다.
- 알람을 삭제할 수 있습니다.
- 알람을 켜거나 끌 수 있습니다.
- 알람에 해당하는 로그(Lucene 쿼리)를 조회할 수 있습니다.
- 알람 발생 내역을 확인할 수 있습니다.

![[그림 11 로그 알람 조회]](http://static.toastoven.net/prod_analytics/new_alarm_1_en.png)
<center>[그림 11 로그 알람 조회]</center>

### 발생 수 알람
- 알람 설정 방법은 다음과 같습니다.
    - 알람 제목: 알람 설정 목록에 표시될 이름을 입력합니다.
    - 검색 조건: 알람 수신을 원하는 로그유형을 Lucene 쿼리로 입력합니다.
    - 알람 규칙: '임계값'에 적용될 부등호를 선택합니다.
    - 임곗값: '검색 조건'에 해당하는 로그가 '알람 규칙' 부등호에 따라 '임계값' 개수만큼 발생하면 알람을 발송합니다.
    - 발생 주기: 분 단위로 입력하며, 입력한 시간 값 내에 로그가 '임계값'만큼 발생해야 알람을 발송합니다.
    - 스누즈: 분 단위로 입력하며, 최소 1분 ~ 최대 1,440분 (24시간) 사이의 값을 설정합니다. (0이면 off)
    - 수신자: 알람을 수신할 수신자를 입력합니다. 각 수신자마다 이메일과 SMS를 선택할 수 있습니다.
    - SMS 알람 문구: 알람 발송 시 SMS로 보낼 문구를 입력합니다.
    - 콜백 수신지: 알람 발송 시 호출될 URL을 입력합니다. http(s):// 와 이메일을 지원합니다.

![[그림 12 발생수 알람]](http://static.toastoven.net/prod_analytics/new_alarm_2_en.png)
<center>[그림 12 발생수 알람]</center>

### 즘감률 알람
원하는 로그유형(Lucene 쿼리)의 발생 증감률에 따라 알람을 발송합니다.

- 알람 설정 방법은 다음과 같습니다.
    - 알람 제목: 알람 설정 목록에 표시될 이름을 입력합니다.
    - 검색 조건: 알람 수신을 원하는 로그유형을 Lucene 쿼리로 입력합니다.
    - 임곗값: '검색 조건'에 해당하는 로그의 증감률입니다. 양수는 로그가 이전 간격 대비 증가한 비율, 0은 이전 간격과 로그 양이 동일, 음수는 이전 간격보다 로그 양이 감소한 비율입니다.
    - 비교 시간: 시간 단위로 입력하며, 입력한 시간 간격과 그 이전 간격 사이의 로그양을 '임계값'에 맞춰 비교합니다. '비교 시간'동안 발생한 로그의 증감률이 '임계값'을 만족하면, 알람을 발송합니다.
    - 스누즈: 분 단위로 입력하며, 최소 1분 ~ 최대 1,440분 (24시간) 사이의 값을 설정합니다. (0이면 off)
    - 수신자: 알람을 수신할 수신자를 입력합니다. 각 수신자마다 이메일과 SMS를 선택할 수 있습니다.
    - SMS 알람 문구: 알람 발송 시 SMS로 보낼 문구를 입력합니다.
    - 콜백 수신지: 알람 발송 시 호출될 URL을 입력합니다. http(s):// 와 이메일을 지원합니다.

![[그림 13 증감률 알람]](http://static.toastoven.net/prod_analytics/new_alarm_3_en.png)
<center>[그림 13 증감률 알람]</center>

### 로그 알람 발생 이력 조회

로그 알람이 발생한 이력을 조회합니다.

- 로그 알람 화면에서 이력 조회(번개) 버튼을 누르면 알람 발생 이력을 확인할 수 있습니다.
- 로그 알람 조회/수정 화면에서 [발생 이력] 버튼을 누르면 알람 발생 이력을 확인할 수 있습니다.

### (구) 로그 알람 이력

로그 알람 발송 이력을 조회할 수 있습니다.
- 알람 시간을 기준으로 검색 기간 설정을 통한 검색이 가능하며 버전별 검색 기능 또한 제공합니다.
- 알람시간, 버전, 로그 레벨, 임계값, 발송방식(SMS/Email), 이벤트 수 및 발송 성공 여부를 제공합니다.
- 또한, 각 행을 클릭하면 상세 로그 메시지와 로그 규칙 정보를 확인할 수 있습니다.

![[그림 14 로그 알람 이력]](http://static.toastoven.net/prod_analytics/alarm_01_en.png)
<center>[그림 14 로그 알람 이력]</center>

### (구) 로그 알람 설정

로그 알람 목록 조회 및 등록/수정/삭제 기능을 제공합니다. 알람 설정 방법은 다음과 같습니다.

- 알람 이름: 알람 설정 목록에 표시될 이름을 입력합니다.
- 로그 레벨: ALL, TRACE, DEBUG, INFO, NOTICD, WARNING, ERROR, FATAL, ALERT, EMERG 중 하나의 값을 선택합니다.
- 규칙 추가: “규칙 추가” 링크를 클릭하여 하나 이상의 필터링 규칙을 추가할 수 있습니다.
- 필터링 규칙: 검색 필드, 포함 문자열, 비포함 문자열 설정 및 정규식 사용 여부를 설정합니다.
- 검색 필드: Settings > 검색 필드 메뉴에서 등록한 검색 필드 중 분석 여부가 false인 검색 필드를 선택할 수 있습니다.
- 포함 문자열: 검색 필드에 포함될 문자열을 입력합니다.
- 알람 유형: '발생 건수' 와 '증감율'중 선택합니다.
- 임계값: 알람 유형이 '발생 건수'인 경우 하나의 '알람 주기' 내에 로그량에 대한 임계값을 설정 합니다. 알람 유형이 '증감율'인 경우 '비교 시간' 대비 증가/감소 비율을 임계값으로 설정합니다.
- 알람 주기: 분단위로 입력할 수 있으며 최소 1분 ~ 최대 60분 사이의 값을 설정 합니다.
- 비교 주기: 시간단위로 입력할 수 있으며 1시간 ~ 24시간 사이의 값을 설정합니다.
- Snooze: 분단위로 입력할 수 있으며 최소 1분 ~ 최대 1,440분(24시간) 사이의 값을 설정합니다. (0이면 off)
- 설명: 알람에 대한 설명을 기술합니다.
- 알람 수신자 설정: 프로젝트 멤버 중 알람을 수신할 멤버들을 선택합니다.
- 콜백URL: 알람이 발생하면 호출될 URL을 설정합니다. http://로 시작하는 형식을 지원합니다.

![[그림 15 로그 알람 설정/등록]](http://static.toastoven.net/prod_analytics/alarm_02_en.png)
![[그림 15 로그 알람 설정/등록]](http://static.toastoven.net/prod_analytics/alarm_03_en.png)
<center>[그림 15 로그 알람 설정/등록]</center>

### 크래시 알람 설정

크래시 로그에 대한 알람을 별도로 설정하는 기능으로 플랫폼(iOS, Android, Unity)별로 각각 하나씩 등록 가능합니다.

알람 설정 방법은 다음과 같습니다.

- 플랫폼 선택: 알람 발생 대상 플랫폼을 iOS, Android, Unity 중 하나로 지정합니다.
- 알람 발생 여부: 알람 발생을 On/Off 처리할 수 있습니다.
- SMS 알림문구 사용: 활성화하면 장애 내용 대신 SMS 알람 문구에 입력된 내용이 SMS로 전송됩니다.
- 임계치: 크래시 발생 빈도수와 평균 빈도수 중 하나를 선택하여 임계치를 입력합니다. 탐지 주기는 10분 입니다.
- 알람 수신자: 프로젝트 멤버 목록에서 알람을 수신할 사용자의 이메일, SMS를 선택합니다.

![[그림 16 크래시 알람 설정]](http://static.toastoven.net/prod_analytics/alarm_04_en.png)
<center>[그림 16 크래시 알람 설정]</center>

### 사용자기반 알람설정

크래시를 겪은 사용자 비율이 임계치(%) 이상인 경우 지정된 사용자의 폰 또는 이메일로 알람을 전송하는 기는을 제공합니다.

알람 설정 방법은 다음과 같습니다.

- 플랫폼 선택: 알람 발생 대상 플랫폼을 iOS, Android, Unity 중 하나로 지정합니다.
- 알람 발생 여부: 알람 발생을 ON/OFF 처리 할 수 있습니다.
- SMS 알람문구 사용: 활성화 하면 장애 내용 대신 SMS알람 문구에 입력된 내용이 SMS로 전송됩니다.
- 임계치: 크래시를 겪은 사용자 비율이 임계치(%) 이상인 경우 지정된 사용자의 폰 또는 이메일로 알람을 전송합니다.
- 알람 수신자: 프로젝트 멤버 목록에서 알람을 수신할 사용자의 이메일, SMS를 선택합니다.

![[그림 16-1 사용자기반 알람 설정]](http://static.toastoven.net/prod_analytics/alarm_05_en.png)
<center>[그림 16-1 사용자기반 알람 설정]</center>

## 설정

검색 필드 관리, 이슈 트래커 설정, 심볼 파일 관리 등 서비스에 필요한 설정을 관리합니다.

```
[Analytics] > [Log & Crash Search] > [Setting] 클릭
```

### 검색 필드

로그 검색 시 사용되는 검색 필드를 조회하는 기능으로 시스템 필드인 기본 필드 목록 외에 사용자 전송 필드인 커스텀 필드를 확인할 수 있습니다.

![[그림 17 검색 필드 설정]](http://static.toastoven.net/prod_analytics/setting_01_en.png)
<center>[그림 17 검색 필드 설정]</center>

1. 로그 전송 시 필드 이름이 txt로 시작하는 경우 분석여부가 true로 설정되고, 그 외에는 분석 여부가 false로 설정됩니다. 분석 여부가 false 인경우 로그 검색의 검색 필드로 등록하여 사용할 수 있습니다.
2. 로그 파일이나 바이너리 파일을 전송하고 로그 검색 화면에서 [다운로드|보기] 링크를 이용하고자 하는 경우, UserBinaryData 혹은 UserTxtData라는 이름의 필드에 base64 인코딩된 값을 담아 전송하시기 바랍니다.

### 이슈 트래킹

이슈 트래커를 설정하면 다음과 같이 App Crach Search > 이슈 조회 페이지의 이슈 목록 클릭 시 이동하는 Error Detail 페이지(그림 6 참고)에서 해당 에러를 이슈 트래커에 등록하여 관리할 수 있습니다.

- 플랫폼: iOS, Android, Unity 중 하나의 플랫폼을 선택합니다. 이슈 트래커는 플랫폼별로 각각 하나씩 설정 가능합니다.
- 이슈 트래커: GitHub, GitLab 중 하나를 선택합니다.
- Issue Title Format: 이슈 제목에 버전 및 위치 정보를 포함 시킬지 여부를 선택합니다.
- GitHub 프로젝트 URL: 이슈 트래커를 GitHub로 선택할 경우 https://github.com/{user}/{project} 형식의 URL을 입력합니다.
- Access token: 이슈 트래커를 GitHub로 선택할 경우 GitHub에서 생성한 Access token을 입력합니다. (참고: https://help.github.com/articles/creating-an-access-token-for-command-line-use)
- GitLab 프로젝트 URL: 이슈 트래커를 GitLab으로 선택할 경우 http://{baseUrl}/{namespace}/{project} 형식의 URL을 입력합니다.
- Private token: 이슈 트래커를 GitLab으로 선택할 경우 GitLab 사이트의 My profile - Account에서 생성한 token값을 입력합니다.
- 테스트: 설정이 정상적인지를 체크합니다.

![[그림 18 이슈 트래커 설정]](http://static.toastoven.net/prod_logncrash/setting_02_en.png)
<center>[그림 18 이슈 트래커 설정]</center>

### 심볼 파일

Symbolication file이 등록 되어 있어야 크래시 로그를 확인할 수 있습니다. 이 메뉴에서는 Symbolication file을 업로드/다운로드/삭제할 수 있습니다.

- iOS: iOS 심볼리케이션 파일을 업로드 할 때에는 ZIP 압축방법으로 BundleName.app.dSYM 파일을 압축하십시오.
- Android: 안드로이드 심볼리케이션을 업로드 할 때에는 mapping.txt 파일을 업로드 해야 합니다.
- Android-NDK: 안드로이드 NDK파일을 업로드 할 때에는 ZIP 압축방법으로 lib.so 파일을 압축하십시오.
- Windows: Windows 심볼리케이션 파일을 업로드 할때는, ZIP 압축방법으로 BundleName.sym 파일을 압축하십시오.
- 심볼 파일의 최대 크기는 200MB 입니다.
- 안드로이드 NDK 심볼리케이션 파일이 허용하는 최대 파일 사이즈를 초과할 경우 원본 ‘lib.so’ 바이너리 파일의 텍스트 형태 심볼을 포함하고 있는 하나의 ‘lib.so.sym’을 포함하는 ZIP 파일의 형태로 업로드 하실 수 있습니다.

![[그림 19 심볼 파일 관리]](http://static.toastoven.net/prod_logncrash/setting_03_en.png)
<center>[그림 19 심볼 파일 관리]</center>

### 로그 보관 기간

로그 보관 기간을 설정합니다.

- 로그 보관 기간은 1개월/2개월/3개월/6개월/1년 중에서 선택할 수 있으며 월 1회에 한해 변경 가능합니다.
- 로그 보관 기간이 지난 데이터는 익일 새벽 삭제됩니다.

![[그림 20 로그 보관 기간]](http://static.toastoven.net/prod_logncrash/setting_04_en.png)
<center>[그림 20 로그 보관 기간]</center>

### 로그 전송 설정

서비스별 로그 전송 여부를 설정합니다.

- 일반로그, 크래시 로그, Network Insights 로그 각각에 대해 전송 여부를 설정할 수 있습니다.
- 설정을 저장한 뒤 APP을 재시작 하면 적용됩니다.

![[그림 21 로그 전송 설정]](http://static.toastoven.net/prod_logncrash/setting_06_en.png)
<center>[그림 21 로그 전송 설정]</center>

## Network Insights

Log & Crash Search SDK에서 전송한 지연시간과 에려율을 타임라인 차트와 URL 목록, 지도로 표시 합니다.

- SDK에서는 클라이언트로부터 URL 설정 화면에서 설정한 URL까지 요청의 지연시간(Letency)과 상태 값(Status)을 Log & Crash Search로 전송합니다.
- 모니터링, 지표 화면에서 현재 플랫폼과 필터를 설정하고 지연시간과 에러율을 확인할 수 있습니다.

```
[Analytics] > [Log & Crash Search] > [Network Insights] 클릭
```

### 모니터링

- 지연시간과 에려율을 타임라인 차트와 URL 목록으로 표시 합니다. 

|항목|	설명|
|---|---|
|필터 조건 | - 최근: 최근 15분, 60분, 24시간, 48시간동안의 조건동안의 시간별 조회 필터, 사용자 지정은 시작/종료 일자를 선택하여 조회(최대 48시간) <br> - 앱 버전: 앱 버전별 조회 필터 <br> - OS 버전: OS 버전별 조회 필터 <br> - 디바이스: 디바이스명 입력
