FROM pytorch/pytorch:1.9.0-cuda11.1-cudnn8-runtime
WORKDIR /tgdlf
COPY . .
RUN sed -i s@/archive.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    sed -i s@/security.ubuntu.com/@/mirrors.aliyun.com/@g /etc/apt/sources.list && \
    apt update && \
    apt install -y vim
RUN pip config set global.index-url http://mirrors.aliyun.com/pypi/simple \
    && pip config set install.trusted-host mirrors.aliyun.com \
    && pip install --disable-pip-version-check -r requirements.txt \
    && cd /tgdlf/enn && python setup.py install \
    && cd /tgdlf && python setup.py install
CMD /bin/bash
