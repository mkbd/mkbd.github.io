
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
# 참고
- [직방히트뒤에다음지도있었다](https://twitter.com/channyun/status/563160698914492416)
- [oauth 인증 ]http://puravidaapps.com/oauth.php
- redirect url urn:ieft:wg:oauth:2.0:oobhttp://localhost


