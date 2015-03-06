## 응모앱

## 순서 
read  특정 페이지 크롤링
데이터 추출 // 신규 내용 감지
크롤 정제 저장 데이터 선정

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

xpath
/html/body/center/table/tbody/tr/td[2]/table/tbody/tr/td/form/table[2]/tbody/tr/td[3]


목록 list -row example
http://www.hansatoy.kr/board/board.html?code=hansatoy_board6&page=1&s_id=&stext=&ssubject=&shname=&scontent=&sbrand=&datekey=&branduid=
url : http://www.hansatoy.kr/board/
pram : board.html?code=hansatoy_board6&page=1&s_id=&stext=&ssubject=&shname=&scontent=&sbrand=&datekey=&branduid=

http://www.hansatoy.kr/board
      /board.html?code=hansatoy_board6&page=1&s_id=&stext=&ssubject=&shname=&scontent=&sbrand=&datekey=&branduid=

```
<tr class="bl_evenline">
    <td class='bl_list bl_no'>83</td>
    <td class='bl_list bl_icon'><img src='/board/images/b2_default.gif' border=0></a></td>
	<td class='bl_list bl_subject leftalign' colspan="1">
        <img src="/shopimages/hansatoy/MK_hansatoy_board6_head.gif" style='margin-right:5px;' align='absmiddle' /><span class='BoardBrandName'></span><a href="board.html?code=hansatoy_board6&page=1&type=v&num1=999957&num2=00000&lock=N"  >[한사토이 체험단] 39번째 엄마, 아빠를 모집합니다. (기간 1월 18일까지)</a>&nbsp;<span class='bl_commtstyle'>(30)</span>&nbsp;
    </td>
    <td class='bl_list bl_name'><div style='padding-left:2px; padding-right:2px;'><img src='/shopimages/hansatoy/MK_hansatoy_board6_adminimg.gif' border=0></div></td>
    <td class='bl_list bl_date'><span class='bl_oldcontent'>2015/01/02</span></td>
    <td class='bl_list bl_hits'>1013</td>
</tr>

<a href="board.html?code=hansatoy_board6&page=1&type=v&num1=999957&num2=00000&lock=N"  >[한사토이 체험단] 39번째 엄마, 아빠를 모집합니다. (기간 1월 18일까지)</a>
```

목록 리스트
아이디 | 제목 | 등록일
bl_no | bl_subject | bl_date

댓글 리스트
아이디 | 아이템번호 | 아이템명 |

 table 이벤트(hs_event)
 회차/타이틀/마감날짜/ 마감일 / 본문내용 img url
 id  / title  / cont_img_url / closedttm / regdttm
 회차가 같으면 안들어감
 
 ```
 create table hs_event(
 id int(11) not null auto_increment comment 'id',
 title  varchar(100) not null comment '제목',
 cont_img_url  varchar(200) not null  comment '본문이미지',
 closedttm timestamp not null default current_timestamp comment '종료일',
 regdttm timestamp not null default current_timestamp comment '등록일',
 PRIMARY KEY (id)
)
 ```

 table item(hs_item)
 id / event_id / name
 id 회차가 같으면 안들어감
 
 ```
 create table hs_item(
  id int(11) not null auto_increment comment 'id',
  event_id int(5) comment 'event id',
  name varchar(100) comment '아이템명',
  PRIMARY KEY (id)
 )
 ```

### 목록 html
[이벤트목록리스트](hansa_board_list.html)
주소 http://www.hansatoy.kr/board
pram board.html?code=hansatoy_board6&page=1  &s_id=&stext=&ssubject=&shname=&scontent=&sbrand=&datekey=&branduid=


개별 item - 상세
주소 http://www.hansatoy.kr/board
pram board.html?code=hansatoy_board6&page=1 &type=v&num1=999957&num2=00000&lock=N

