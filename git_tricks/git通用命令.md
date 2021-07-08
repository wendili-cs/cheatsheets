# Git常用指令
1. 设置远程仓库
```bash
git remote set-url origin <远程仓库URL>
```
2. 将本地分支与远程同名分支相关联
```bash
git push --set-upstream origin <本地分支名>
// 简写方式
git push -u origin <本地分支名>
```

3. 查看本地分支
```bash
git branch
```

4. 本地指定分支push到远程指定分支
```bash
git push origin <本地分支名>:<远程分支名>
```