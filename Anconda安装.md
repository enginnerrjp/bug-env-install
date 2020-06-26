##环境变量配置，加入到系统变量
* anaconda安装路径（为了Python检查正常）:前面安装时路径一定要记清楚，我的默认是D:\anaconda3
* 安装路径\scripts（为了conda检查正常）:只需在上述路径中找到scripts，然后复制路径即可，我的默认路径是D:\Anaconda3\Scripts

* 上述两个环境变量都是通过：此电脑—右键—高级系统设置—环境变量—系统变量—双击path—新建这两个变量即可。


##换源
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/msys2/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    conda config --set show_channel_urls yes

* conda info 查看

##   附pip换源
```
* Windows环境，在C:\user\username\pip\pip.ini（自行创建）中加入

    [global]
    index-url=https://pypi.tuna.tsinghua.edu.cn/simple 
    [install]  
    trusted-host=pypi.tuna.tsinghua.edu.cn
    disable-pip-version-check = true  
    timeout = 6000 '''

* Linux环境
    cd ~/
    mkdir .pip
    cd .pip
    sudo vim pip.conf

    [global]
    index-url=https://pypi.tuna.tsinghua.edu.cn/simple 
    [install]  
    trusted-host=pypi.tuna.tsinghua.edu.cn
    disable-pip-version-check = true  
    timeout = 6000
```
##虚拟环境
```
1. conda env list 或 conda info -e 查看当前存在哪些虚拟环境

2. conda update conda 检查更新当前conda

3. conda update --all 更新本地已安装的包

4. conda create -n your_env_name python=X.X（2.7、3.6等） anaconda 命令创建python版本为X.X、名字为your_env_name的虚拟环境。your_env_name文件可以在Anaconda安装目录envs文件下找到。

5. Windows: activate your_env_name(虚拟环境名称) 激活虚拟环境

6. conda install -n your_env_name [package] 安装package到your_env_name中

7. linux: source deactivate           Windows: deactivate     关闭虚拟环境

8. conda remove -n your_env_name(虚拟环境名称) --all 删除虚拟环境

9. conda remove --name your_env_name package_name  删除环境中的某个包
```
##相关bug
```
bug info :CondaHTTPError: HTTP 000 CONNECTION FAILED for url XXXXXX
修改 C:\Users\xxx\.condarc为以下内容

ssl_verify: true
show_channel_urls: true

channels:
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/win-64/
  - http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/win-64
```


##tensorflow 安装
* 参考[csdn](https://blog.csdn.net/weixin_44498793/article/details/103962196 '3.7+2.0(GPU)')




