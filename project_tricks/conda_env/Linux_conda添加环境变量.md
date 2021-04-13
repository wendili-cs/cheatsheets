链接：https://blog.csdn.net/u014611178/article/details/107833929

## 步骤

1. 进入conda虚拟环境，比如：`/home/shared_user/miniconda3/envs/wendi_py38`
2. 创建`activate.d`和`deactivate.d`文件夹，并新建对应的sh脚本：
```
mkdir -p ./etc/conda/activate.d
mkdir -p ./etc/conda/deactivate.d
touch ./etc/conda/activate.d/env_vars.sh
touch ./etc/conda/deactivate.d/env_vars.sh
```
3. 在`activate.d`的`env_vars.sh`脚本中添加激活环境时的环境变量，多个的话用``:``分隔，例如：
```sh
export PYTHONPATH="/home/repos/myproject":"/home/repos/myproject/libs"
```
4. 在`deactivate.d`的`env_vars.sh`脚本中添加退出环境时执行的语句：
```sh
unset PYTHONPATH
```
5. 可以在激活环境后，用`echo $PYTHONPATH`查看是否成功执行sh脚本。
```
echo $PYTHONPATH
```