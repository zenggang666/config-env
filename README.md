# config-env
环境配置
#查看当前存在哪些虚拟环境
conda env list

切换到目标文件夹=>创建新环境(创建的环境名称，指定python版本)=>激活创建的环境=>添加（配置）镜像文件

conda create -n pytorch python=3.7

conda activate pytorch

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/

conda install [package-name]

# 此处应该先添加镜像文件，再创建环境，否则可能因为网速慢而导致下载失败
# 配置国内源，方便安装Numpy,Matplotlib等

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/

# 配置国内源，安装PyTorch用

conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/

# 显示源地址

conda config --set show_channel_urls yes

#显示已经添加的镜像文件

conda config --show channels

#删除指定的镜像文件

conda config --remove channels https://...


#conda修改环境名称（先克隆旧的环境）

conda create --name new-name --clone old-name

conda remove --name old-name --all

#删除虚拟环境中的包

conda remove --name your-env-name package-name

#删除虚拟环境
conda remove -n your-env-name --all

##################################################################
win10下安装cuda10.2和cudnn7.6.5
如果是新机器，首先用鲁大师更新最新的显卡驱动
然后去英伟达官网下载cuda和cudnn并安装
CUDA下载页面：https://developer.nvidia.com/cuda-downloads
cuDNN下载页面：https://developer.nvidia.com/rdp/cudnn-download

安装CUDA和cuDNN
找到你下载的CUDA，无脑安装就行了。当然如果你想自定义的话要记住你选择的安装路径（直接默认路径）。
CUDA安装完成后，打开powershell，执行nvcc -V ，成功的话会返回cuda版本号。
解压cuDNN压缩包，可以看到bin、include、lib目录
打开 C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA（cuda安装路径）
找到你安装的版本目录，打开，找到bin、include、lib目录，将cuDNN压缩包内对应的文件复制到bin、include、lib目录。
注意：是复制文件到bin、include、lib目录，不是复制目录。

添加环境变量
你需要在 系统环境变量的Path项 下添加几个路径
点击 编辑 – > 新建、浏览
需要添加下面两个路径，这就是说为什么要记住你的安装路径了，我使用的是默认的安装路径。

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.2

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.2\lib\x64

注意：选择你安装的路径

检查安装结果
打开 C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.2\extras\demo_suite
=> cd  C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.2\extras\demo_suite
在此路径下打开powershell执行：
=> .\bandwidthTest.exe
接着执行：
=> .\deviceQuery.exe


