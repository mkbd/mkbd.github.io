
## 개요
- 예매가 성행으로 오픈 직후 마감됨
- 허수가 많다 즉 취소가 많다
- 마냥 빈자리가 날때까지 기다릴 수 가 없구나

## 재료
인터파크 예매 url
http://ticket.interpark.com/Ticket/Goods/GoodsInfo.asp?GoodsCode=15001801

```
GET http://ticket.interpark.com/Ticket/Goods/GoodsInfoJSON.asp?Flag=RemainSeat&GoodsCode=15001801&PlaceCode=14000312&PlaySeq=008&Callback=fnPlaySeqChangeCallBack HTTP/1.1
headers = {'Referer': 'http://ticket.interpark.com/Ticket/Goods/GoodsInfo.asp?GoodsCode=15001801'}
```
- Referer 체크하나 봅니다.

## 알림받을꺼
- 마플봇은 이제 못쓰나 봅니다. http://dna.daum.net/apis/mypeople/intro
- 카톡을 정작 메시지api 는 지원 안하네요;
- 트윗으로 알람을 보내야 할까 봅니다.

## 어이만들고
- 체크
- ok 홀딩 1분
- 다시 체크

```
__author__ = 'dubu'
#!/usr/bin/python
#-*- coding: utf-8 -*-
import requests
import json
import time

#from __future__ import absolute_import, print_function
import tweepy

headers = {'Referer': 'http://ticket.interpark.com/Ticket/Goods/GoodsInfo.asp?GoodsCode=15001801'}

while(True):
        for i in ['003','004','005','006','007','008','009','010','011','014','015','016']:
        #for i in ['003']:
                r = requests.get('http://ticket.interpark.com/Ticket/Goods/GoodsInfoJSON.asp?Flag=RemainSeat&GoodsCode=15001801&PlaceCode=14000312&PlaySeq='+i+'&Callback=fnPlaySeqChangeCallBack', headers=headers)
                #r.encoding = 'euc-kr'
                #print(r.json()['RemainCnt'])
                cont = r.text.replace('fnPlaySeqChangeCallBack({"JSON":[','')
                cont = cont.replace(']});','').encode('ascii', 'ignore').decode('ascii')
                cont = cont.replace("'", "\"")
                j = json.loads(cont)
                #print(type(j))
                #print(j['RemainCnt'])
                remainSeat = j['RemainCnt']
                if(remainSeat != '0'):
                        #print i
                        print time.strftime("%Y/%m/%d %H:%M:%S", time.localtime())
                        print 'gogogo!! seat'
                        print(j['RemainCnt'])

                        # twitter
                        consumer_key="#consumer_key#"
                        consumer_secret="#consumer_secret#"

                        access_token="#access_token#"
                        access_token_secret="#access_token_secret#"

                        auth = tweepy.OAuthHandler(consumer_key, consumer_secret)
                        auth.secure = True
                        auth.set_access_token(access_token, access_token_secret)

                        api = tweepy.API(auth)
                        msg = time.strftime("%Y/%m/%d %H:%M:%S @kozazz ", time.localtime()) + i+ 'day gogogo!!  ' +j['RemainCnt']

                        api.update_status(status=msg)
                else:
                        #print time.strftime("%Y/%m/%d %H:%M:%S", time.localtime())
                        #print 'no seat;;'
                        print( '.')

        time.sleep(60)
```

![inter](/doc/img/inter_seat.jpg)