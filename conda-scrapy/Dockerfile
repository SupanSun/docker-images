
FROM debian:latest
MAINTAINER xxx Team <1036097498@qq.com>

RUN apt-get update && apt-get -y install wget bzip2 \
    && wget -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/Miniconda3-latest-Linux-x86_64.sh \
    && bash Miniconda3-latest-Linux-x86_64.sh -bfp /root/conda \
    && rm Miniconda3-latest-Linux-x86_64.sh 
    
ENV PATH=/root/conda/bin:$PATH
RUN ln -s /bin/bash /bin/sh  -f
RUN export PATH=/root/conda/bin:$PATH
RUN conda install -y python=3.7 \
    && conda update conda \
    && apt-get -qq -y remove bzip2 curl \
    && apt-get -qq -y autoremove \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/* /var/log/dpkg.log \
    && conda clean --all --yes \
    && apt-get -y install ssh  \
    && conda create -n python3.7 numpy matplotlib python=3.7 \
    && activate python3.7

RUN pip install -r soft-pip.txt
RUN conda install -r soft-conda.txt


## 
EXPOSE 80
EXPOSE 22
EXPOSE 8080
EXPOSE 5000
EXPOSE 9000




CMD ["/bin/bash","/etc/init.d/ssh"]

