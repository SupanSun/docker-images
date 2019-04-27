# docker-images
## 手动安装miniconda3

### 在linux在使用以下命令下载miniconda
wget -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh 

### 安装刚刚下载的Miniconda，bash就是运行.sh文件的意思
bash Miniconda3-latest-Linux-x86_64.sh -bfp /root/conda 

### 添加环境变量
echo 'PATH=/root/conda/linuxc:$PATH' >> .bashrc 
### 重启配置
source .bashrc

### 成功
conda --version 

