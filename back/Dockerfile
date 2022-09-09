FROM python:3.10.6
ENV PYTHONUNBUFFERED 1
#アプリのディレクトリ作成
RUN mkdir /opt/app
#uwsgiログファイル作成
RUN mkdir -p /var/log/uwsgi/ && touch uwsgi.log
# 各種命令実行のカレントディレクトリを指定
WORKDIR /opt/app
# ローカルのrequirements.txtをコンテナ内にコピー
COPY requirements.txt /opt/app/
# コマンド実行
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt
#vimインストール
RUN apt-get update && \
    apt-get install -y vim
COPY . /opt/app/