

## 介绍
在MacOS系统下存在着.DS_Store文件，直接`git add ./`会包含这些无用的内容。

### 步骤
1. 在repo的根目录新建`.gitignore`文件，旨在制定忽视对git文件类型。
2. 在`.gitignore`文件里面添加内容：
```
.gitignore
**/.DS_Store
```
3. 对于已经git push的DS_Store文件，使用`git rm -r --cached .DS_Store`（这个只删除了根目录下的），再git commit和git push。