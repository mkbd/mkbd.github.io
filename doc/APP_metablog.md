# 모든 블로그 app
- appinventor 하고 metawebblog랑 연결쓰기가 불편함. 서버 필요할듯 ㅡ.ㅡ
- MetaWeblogApi 
- 네이버/티스토리/다음블록/wordpress 블로그 공통앱 
- 모바일 심플 블로그앱

#참고 
[metaWebBlog api msdn](https://msdn.microsoft.com/ko-kr/library/bb259697.aspx)
window live writer

# post example

- tistory
```

password = "비번"
blogNum = 485275
blogId = "티스토리이름"

import xmlrpclib
datastruct={'category': '', 'description': '내용입니다','title':'제목입니다.'}
metaWeblog=xmlrpclib.Server("http://blogId.tistory.com/api").metaWeblog
no=metaWeblog.newPost(blogNum, "blogId@hanmail.net","password", datastruct, True)
r = metaWeblog.getPost(no, "blogId@hanmail.net","password")
```
