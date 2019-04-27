
FROM debian:latest
MAINTAINER xxx Team <1036097498@qq.com>

RUN apt-get -qq update && apt-get -qq -y install curl bzip2 \
    && curl -sSL https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -o /tmp/miniconda.sh\
    && bash /tmp/miniconda.sh -bfp /root/conda \
    && rm /tmp/miniconda.sh \
    && conda install -y python=3.7 \
    && conda update conda \
    && apt-get -qq -y remove bzip2 curl \
    && apt-get -qq -y autoremove \
    && apt-get autoclean \
    && rm -rf /var/lib/apt/lists/* /var/log/dpkg.log \
    && conda clean --all --yes 
#    && apt-get install ssh  \
#    && conda create -n python3.7 numpy matplotlib python=3.7 \
#    && activate python3.7
##
ENV PATH /opt/conda/bin:$PATH

RUN pip install -r soft-pip.txt
RUN conda install -r soft-conda.txt


## 
EXPOSE 80
EXPOSE 22
EXPOSE 8080
EXPOSE 5000
EXPOSE 9000




CMD ["/bin/bash","/etc/init.d/ssh"]

