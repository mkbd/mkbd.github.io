## 응모앱

## 순서 
read  특정 페이지 크롤링
데이터 추출 // 신규 내용 감지
크롤 정제 저장 데이터 선정
 
 table 이벤트(hs_event)
 회차/타이틀/마감날짜/ 마감일 / 본문내용 img url
 id  / title / close_date / cont_img_url
 회차가 같으면 안들어감
 
 table item(hs_item)
 id / item_id
 id 회차가 같으면 안들어감

블로그 글 작성  또는 카페, 블로그, 타블로그 전부 괜찮음

#### cronatb  scrapy evnet info

#### write filtered data to db

#### post blog by templet

mybloglist= {tistoyr01,tistoyr02,tistoyr03, naver01, daumblog01, woredpress01}
datastruct={'category': '', 'description': '주저리주저리 내용입니다<br> <img src="http://example.com/aaa.jpg">','title':'000회차 응모합니다'}
for i in  mybloglist
 i.post(datastruct)
 
### comment at event post 특정게시물 로그인/ 댓글 작성



기능
- 댓글리스틑 목록 셈을 통한 확율높은 item선정


url
http://www.hansatoy.kr/board/board.html?code=hansatoy_board6&page=1&type=v&num1=999955&num2=00000&lock=N
http://www.hansatoy.kr/board/board.html?code=hansatoy_board6&page=1&type=v&num1=999956&num2=00000&lock=N

