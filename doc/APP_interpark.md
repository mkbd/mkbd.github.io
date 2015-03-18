
인터파크 예매
http://ticket.interpark.com/Ticket/Goods/GoodsInfo.asp?GoodsCode=15001801

GET http://ticket.interpark.com/Ticket/Goods/GoodsInfoJSON.asp?Flag=RemainSeat&GoodsCode=15001801&PlaceCode=14000312&PlaySeq=008&Callback=fnPlaySeqChangeCallBack HTTP/1.1

http://dna.daum.net/apis/mypeople/intro

- 체크
- ok 홀딩 10분
- 다시 체크


```
__author__ = 'dubu'
#!/usr/bin/python
#-*- coding: utf-8 -*-
import requests
import json
import time
headers = {'Referer': 'http://ticket.interpark.com/Ticket/Goods/GoodsInfo.asp?GoodsCode=15001801'}

while(True):
        for i in ['003','004','005','006','007','008','009','010','011','014','015','016']:
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
                        print i
                        print time.strftime("%Y/%m/%d %H:%M:%S", time.localtime())
                        print 'gogogo!! seat'
                        print(j['RemainCnt'])
                #else:
                        #print time.strftime("%Y/%m/%d %H:%M:%S", time.localtime())
                        #print 'no seat;;'
                        print '.'

        time.sleep(60)
```