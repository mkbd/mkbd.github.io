


## 앱다운로드
- [easy_today_jjal.apk](/doc/apk/todayJJal/easy_today_jjal.apk)

## 스냅샷
- ![preview](/doc/apk/todayJJal/todayJJal.jpg)

## 개요
- 오늘의짤. 일일 선정. 하루 대문장만하게 메인에 노출
- 1page 앱.. 
- 짤등록 이미지url 등록가능.(쉽게 등록가능하게 해줄 필요가 있다.)
- 등록된 짤이미지는 제한한다 (10개 가정)
- 동록된 짤이미지가 최대개수(10개가정)이면 등록을 하지 못한다.
- \[공격기능\]등록된 짤이미지중 싫어요 체크 가능 싫어요 체크가 된 이미지 중 특정시간이 지난 이미지는 삭제된다. (예 24시간)
- \[삭제기능\] 삭제가 안되기 위하여. 싫어요 체크를 삭제가능하다.
- 공격방어 시간을 정할까.. ;;  평일 19:00 ~ 22:00, 주말 10:00 ~ 22:00

# 대충 설계
j1~10 존재.

타이머 초카운트

(삭제공격)
(삭제취소)
(url 등록)

입력 (등록)

id | jal_url | mark_time
j1 | http://makeduck.github.io/img/jal/j1.gif | 1501261050.30 |
j2 | http://makeduck.github.io/img/jal/j1.gif |                  |
j3 | http://makeduck.github.io/img/jal/j1.gif | 1501261050 |
j4 | http://makeduck.github.io/img/jal/j1.gif |                  |
j5 | http://makeduck.github.io/img/jal/j1.gif |                  |
j6 | http://makeduck.github.io/img/jal/j1.gif |                  |
j7 | http://makeduck.github.io/img/jal/j1.gif | 1501261050 |
j8 | http://makeduck.github.io/img/jal/j1.gif |                  |
j9 | http://makeduck.github.io/img/jal/j1.gif |                  |
j10 | http://makeduck.github.io/img/jal/j1.gif |                  |

()()()()()()()()

## 짤그림 예시
![j1](http://makeduck.github.io/img/jal/j1.gif)
![j2](http://makeduck.github.io/img/jal/j2.gif)
![j3](http://makeduck.github.io/img/jal/j3.gif)
![j4](http://makeduck.github.io/img/jal/j4.gif)
![j5](http://makeduck.github.io/img/jal/j5.gif)

![j6](http://makeduck.github.io/img/jal/j6.gif)
![j7](http://makeduck.github.io/img/jal/j7.gif)
![j8](http://makeduck.github.io/img/jal/j8.gif)
![j9](http://makeduck.github.io/img/jal/j9.gif)
![j10](http://makeduck.github.io/img/jal/j10.gif)

![j11](http://makeduck.github.io/img/jal/j11.gif)
![j12](http://makeduck.github.io/img/jal/j12.gif)
![j13](http://makeduck.github.io/img/jal/j13.gif)
![j14](http://makeduck.github.io/img/jal/j14.gif)
![j15](http://makeduck.github.io/img/jal/j15.gif)

![j16](http://makeduck.github.io/img/jal/j16.gif)
![j17](http://makeduck.github.io/img/jal/j17.gif)
![j18](http://makeduck.github.io/img/jal/j18.gif)
![j19](http://makeduck.github.io/img/jal/j19.gif)
![j20](http://makeduck.github.io/img/jal/j20.gif)

