## 扫盲

### 0X1蜜罐：

蜜罐（本质上是诱饵网络可访问资源）可以作为监视和预警工具部署在网络中，因为蜜罐通常不会出于合法目的而被访问。

期间和攻击后，攻击者所使用的试图破坏这些诱饵资源技术进行了研究，以保持眼睛上新开发技术。  
这种分析可用于进一步加强蜜罐保护的实际网络的安全性。蜜罐还可以将攻击者的注意力从合法服务器上移开。

蜜罐鼓励攻击者将时间和精力花在诱饵服务器上，同时分散他们对真实服务器上数据的注意力。  
与蜜罐类似，蜜网是设置有故意漏洞的网络。其目的还在于邀请攻击，以便可以研究攻击者的方法，并且可以使用该信息来提高网络安全性。  
蜜网通常包含一个或多个蜜罐

### 0X2 WAF:

WAF技术支持：[http://netsecurity.51cto.com/art/201007/210828.htm](http://netsecurity.51cto.com/art/201007/210828.htm)  
WAF和IPS区别：[http://netsecurity.51cto.com/art/201007/214156.htm](http://netsecurity.51cto.com/art/201007/214156.htm)

### 0X3 Nginx：

Nginx：  
    [https://juejin.im/entry/57fb07b0816dfa0056c0ada8](https://juejin.im/entry/57fb07b0816dfa0056c0ada8)

### 0X4 Linux系统下查看已经登录用户并踢出

1. w   ////  who   
2. 查看某用户：w + 用户名
3. 踢出已登录的用户：pkill -KILL -t pts/0 \(pts/0为w指令看到的用户终端号\) [链接](https://blog.csdn.net/cloudeagle_bupt/article/details/9628779)

### 0X5 VIM 使用：

1. 查找：  /  从上到下查找 ？ 从下往上

2. 复制操作：小写yy 复制单行，nyy复制n行

3. 粘贴：小写p 粘贴当前光标到下一行 大写P

4. 删除：dd删除当前行 2dd 删除光标处当前两行，2，66d; 删除多行

5. 增加空行  小写o 当前下一行，大写O当前上一行

6. 替换，  
   行替换   ：s/被替换对象/新对象/gc，提示后按y即完成替换  
   全文替换 ：%s/被替换对象/新对象/gc，分别按行提示后按y即完成替换。

7. 撤销与回复  
    小写u：change before（按行，分步骤以时间轴为单位撤销最近的动作）直至already at oldest change（可撤销多步）；  
    大写U：仅撤销一步操作  
    chrl+ r 一步   ctrl+ R 一步到底

### OX6   HTTP状态码

[链接](https://www.cnblogs.com/starof/p/5035119.html)  
10. sdf  
11.

### 0X7 fuck

sudo apt update  
sudo apt install python3-dev python3-pip python3-setuptools  
sudo pip3 install thefuck

[https://github.com/nvbn/thefuck](https://github.com/nvbn/thefuck)

### 0X8 pip 升级之后

sudo gedit /usr/bin/pip  
from pip import main 改为 from pip.\_internal import main

### 0x9 ubuntu中文乱码

[https://www.centos.bz/2017/12/%E8%A7%A3%E5%86%B3ubuntu%E7%9A%84%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E9%97%AE%E9%A2%98/](https://www.centos.bz/2017/12/%E8%A7%A3%E5%86%B3ubuntu%E7%9A%84%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E9%97%AE%E9%A2%98/)



