# 忽略Git的文件模式变化

在macOS上使用git的时候发现一堆文件发生了更改，更改内容为
```
mode change 100755 => 100644
```
## 举措
在git config中设置，忽略文件模式的更改，具体命令为：
```
git config --add core.filemode false
```