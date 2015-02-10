
## oauth2Api(Mashup)공통앱

## 소개
- oauth2 방식으로 공개된 api 많음
- twitter, facebook, tistory, whooing, 다음지도, 비트코인 등 다수 존재
- 이를 아우루는 공통앱을 생성.
- 매시업을 쉽게 할 수 있도록 템플릿화 한다
- 공통된 부분을 정리한다
- 여러앱을 함쳐놓은 것 같이 사용 가능 하다.
- 2차 가공전 1차 webview json 포맷을 이쁘게 보여주는것까지 한다.

## 2차 피벗
-json type in/output api 만드는게 낫지 않는가 또는 api 수준의 앱
- api 만들기 입력 파라메터, output은 formatting 된 json문서
 
## feedly api
- rss feed api
- api summary 

```
Example 1: Get access to the content of the ReadWrite feed
curl 'http://cloud.feedly.com/v3/stream/contents?streamId=feed%2Fhttp%3A%2F%2Fwww.readwriteweb.com%2Frss.xml&count=20' -H 'Authorization: OAuth YourAuthToken'

Example 2: Get access to the personalization graph of an authenticated user
curl 'http://cloud.feedly.com/v3/subscriptions' -H 'Authorization: OAuth YourAuthToken'

Example 3: Get the most popular articles from Engadget
curl 'http://cloud.feedly.com/v3/mixes/contents?streamId=feed%2Fhttp%3A%2F%2Fwww.engadget.com%2Frss.xml&count=3' -H 'Authorization: OAuth YourAuthToken'
```
## whooing api
- [가계부 api](https://whooing.com/#forum/developer/ko/authorization)
- api 지원많음

## move api
- [move api](https://dev.moves-app.com/docs/authentication)
- api summary 
```
GET /user/storyline/daily/<date>[?trackPoints=true/false][&updatedSince=<updatedSince>][&timeZone=<timeZone>]
GET /user/storyline/daily/<week>[?trackPoints=true/false][&updatedSince=<updatedSince>][&timeZone=<timeZone>]
GET /user/storyline/daily/<month>[?updatedSince=<updatedSince>][&timeZone=<timeZone>]
GET /user/storyline/daily?from=<from>&to=<to>[&trackPoints=true/false][&updatedSince=<updatedSince>][&timeZone=<timeZone>]
GET /user/storyline/daily?pastDays=<pastDays>[&trackPoints=true/false][&updatedSince=<updatedSince>][&timeZone=<timeZone>]
```

## 각종 api

# 참고
- [직방히트뒤에다음지도있었다](https://twitter.com/channyun/status/563160698914492416)
- [oauth 인증 ]http://puravidaapps.com/oauth.php
- redirect url urn:ieft:wg:oauth:2.0:oobhttp://localhost


# ideation 
```

token 가져오는 부분.
url 파라미터
url, array pytho 으로  받는게 낫겠다.
api 중계센터?
조회 조건

call list , 조회 조건
리스트 형태 데이터  [클릭] 상세 화면
아이템 수정/추가/삭제

[리스트]  .. 조회   조건[] 멀티 조건을 받기위한 파이썬이 좋은듯.

rest api 형식을 맞추기... 심플화 url, [, ,,, ]  복수가 파라메터.
for repalce firt 하나씩 파라미터 바인드.ㅇ

url 은 먼저 등록
등록된 api 별로 url 먼저 등록, 조회는 파라미터 미리 필요함.
나머지는 공통으로 쓰자.

리스트 조회 여러개
아이템별 key 존재
key 선택시 개별 아이템 상세
key 이용 수정/삭제 가능
목록에서도 노출된 컬럼은 수정 가능.
상세화면에서는 모든 컬럼 항목 수정 가능.
입력/수정 화면은 공통으로 사용

stepi1. 조회 먼저 그냥 구현.

step2. 입력/수정/삭제

```


