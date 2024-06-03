FROM python:3.10-slim

COPY requirements.txt /install/requirements.txt
WORKDIR /workspace

RUN ln -sf /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install --no-install-recommends \
        curl \
        git \
        vim \
        less \
        gcc && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

#　追加パッケージのインストール
RUN pip3 install --upgrade pip
RUN pip install --no-cache-dir --upgrade -r /install/requirements.txt