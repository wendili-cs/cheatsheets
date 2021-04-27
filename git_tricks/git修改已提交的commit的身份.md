

## 介绍
之前从服务器上提交的代码用的默认的global的身份，想把提交的commit身份改回来。

### 链接
https://cloud.tencent.com/developer/article/1352623

### 步骤
#### 重新设置项目身份
```
git config user.name "{自己的用户名}"
git config user.email "{自己的邮箱}"
```

#### 修改过往提交的commit
1. 新建一个.sh文件，如`setNewUser.sh`，并添加内容：
```sh
#!/bin/sh

git filter-branch --env-filter '

OLD_EMAIL="{旧的用户名}"
CORRECT_NAME="{自己的用户名}"
CORRECT_EMAIL="{自己的邮箱}"
# 其实也可以用"$GIT_AUTHOR_EMAIL" = "{旧的邮箱}"

if [ "$GIT_COMMITTER_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_COMMITTER_NAME="$CORRECT_NAME"
    export GIT_COMMITTER_EMAIL="$CORRECT_EMAIL"
fi
if [ "$GIT_AUTHOR_EMAIL" = "$OLD_EMAIL" ]
then
    export GIT_AUTHOR_NAME="$CORRECT_NAME"
    export GIT_AUTHOR_EMAIL="$CORRECT_EMAIL"
fi
' --tag-name-filter cat -- --branches --tags
```
2. 执行此.sh文件
```
./setNewUser.sh
```
3. 扫描修改完成后push到remote
```
git push origin --force --all
```

然后可以看到之前的commit更改过来了。
<p align="center">
  <img src=./imgs/001.png />
</p>

#### repos版本回滚
中途不小心给回滚了，回退到某一版本用
```
git reset --hard {版本号（比如96ee72c3）}
git push origin {branch名称} --force
```