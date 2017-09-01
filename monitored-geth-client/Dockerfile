FROM registry.cn-hangzhou.aliyuncs.com/chit/xping:latest

RUN apk update &&\
    apk add --no-cache --repository http://nl.alpinelinux.org/alpine/v3.6/main nodejs=6.10.3-r1 nodejs-npm=6.10.3-r1 git bash perl

RUN cd /root &&\
    git clone https://github.com/cubedro/eth-net-intelligence-api &&\
    cd eth-net-intelligence-api &&\
    npm install &&\
    npm install -g pm2

ADD start.sh /root/start.sh
ADD app.json /root/eth-net-intelligence-api/app.json
RUN chmod +x /root/start.sh

ENTRYPOINT /root/start.sh
