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
conda remove -n your-env-naem --all
