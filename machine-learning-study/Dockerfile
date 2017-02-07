FROM ubuntu:16.10
MAINTAINER ScenesK

RUN apt-get update && apt-get install -qy \
    bzip2 \
    graphviz \
    g++ \
    libglib2.0-0 \
    libsm6 \
    libxrender1 \
    libxtst6 \
    wget \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*
RUN wget --quiet https://repo.continuum.io/archive/Anaconda3-4.1.1-Linux-x86_64.sh -O ~/anaconda.sh \
 && bash ~/anaconda.sh -b -p /opt/conda \
 && rm ~/anaconda.sh
ENV PATH /opt/conda/bin:$PATH
RUN conda install -qy \
    scikit-learn=0.18 \
    seaborn=0.7
RUN conda install -qy -c conda-forge \
    pydotplus=2.0 \
    tensorflow=0.12
RUN conda install -qy -c alchayward keras=1.1
RUN pip install --upgrade pip \
 && pip install chainer==1.20
VOLUME /root/jupyter
WORKDIR /root/jupyter
ENTRYPOINT ["sh", "-c", "jupyter notebook --no-browser --ip=0.0.0.0 --port=8888"]
