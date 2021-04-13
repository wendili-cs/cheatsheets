# 介绍
这里记录着如何使用XShell远程连接服务器，MobaXterm也很方便，但是普通用户有SSH Tunnel数量限制。

## 直接连接服务器

## 用跳板机连接服务器
这种情况是无法直接连接所需服务器，需要通过`我的电脑-->跳板机-->服务器`的方式访问。

1. 首先，连接跳板机：
<p align="center">
  <img src=./imgs/01.png />
</p>

2. 设置SSH隧道，通过跳板机将服务器的端口转接到本地端口。（如果有多个服务器要连接，可以添加多个TCP/IP转移）
<p align="center">
  <img src=./imgs/02.png />
  <img src=./imgs/03.png />
</p

3. 再创建一个会话，连接转移过来的本地接口，就等同于连接到了远程服务器：
<p align="center">
  <img src=./imgs/04.png />
</p>

4. 如果在服务器上使用Python的juputer notebook，从本地浏览器使用服务器的jupyter notebook，可以再在这个服务器的会话里面添加SSH隧道：
<p align="center">
  <img src=./imgs/05.png />
  <img src=./imgs/06.png />
  <img src=./imgs/07.png />
</p>

5. 然后就可以在浏览器打开jupyter notebook了：
<p align="center">
  <img src=./imgs/08.png />
</p>