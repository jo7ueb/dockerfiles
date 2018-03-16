FROM nvidia/cuda:9.1-cudnn7-devel

# install required packages
RUN apt-get update -y && \
    apt-get install -y --no-install-recommends \
    build-essential \
    ca-certificates \
    git \
    graphviz \
    curl \
    libopenmpi-dev \
    libopencv-dev \
    wget &&\
    rm -rf /var/lib/apt/lists/* /var/cache/apt/archives/*

# install pyenv
RUN git clone git://github.com/yyuu/pyenv.git /root/.pyenv && \
    git clone https://github.com/yyuu/pyenv-pip-rehash.git /root/.pyenv/plugins/pyenv-pip-rehash
ENV PYENV_ROOT /root/.pyenv
ENV PATH $PYENV_ROOT/bin:$PATH
RUN echo 'eval "$(pyenv init -)"' >> .bashrc

# install anaconda
ENV ANACONDA_VER 5.0.1
RUN pyenv install anaconda3-$ANACONDA_VER &&\
    pyenv global anaconda3-$ANACONDA_VER
ENV PATH $PYENV_ROOT/versions/anaconda3-$ANACONDA_VER/bin:$PATH

# update anaconda
RUN conda update -y conda &&\
    pip install --upgrade pip

# install required packages for deep learning
RUN pip install \
    matplotlib \
    opencv-python \
    cupy==2.4.0 \
    chainer==3.4.0 \
    chainercv==0.8.0 \
    chainerrl==0.3.0 \
    chainermn==1.2.0 \
    jupyter \
    gprof2dot
