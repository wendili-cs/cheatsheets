

## 介绍
用git每次push到GitHub上都需要登录，输入密码。因此可以考虑将已有的http的git仓库转换成ssh的。

### 链接
https://blog.csdn.net/xl_1851252/article/details/81274721

### 步骤
1. 添加ssh公钥
```
ssh-keygen -t rsa
```
2. 将`id_rsa.pub`公钥文件上传到GitHub。
3. 在本地的git路径下找到`.git/config`文件，更改其中的url，将原本的：
```
https://github.com/{用户名}/{仓库名}.git
```
更改为
```
git@github.com:{用户名}/{仓库名}.git
```