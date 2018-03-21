# Wordpress XSS exploit 
Wordpress XSS exploit demo

<img src="week7_xss_exploit.gif" width="800">

[!] Title: WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
    Reference: https://wpvulndb.com/vulnerabilities/7945
    Reference: http://klikki.fi/adv/wordpress2.html
    Reference: http://packetstormsecurity.com/files/131644/
    Reference: https://www.exploit-db.com/exploits/36844/
[i] Fixed in: 4.2.1 

Description: 
Hacker can inject JavaScript in WordPress comments. The script is executed when comment is viewed. The comment has to be longer than 64 kb, because this is the maximum size of the text field in MySQL

Step by step:
1. I left a harmless comment under the post to bypass the initial moderation. For the second comment of the same post you won't have to go through the moderation again.
2. I left a long comment to get an alert "Hello World" :
```html
<a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a>
```
3. When the admin will go to the page where the post is located the injected javascript will be executed and we can see the alert box "Hello world". The same way using different code we can gain access to cookies and to everything that logged in admin can do.




# Wordpress SQLI exploit 
