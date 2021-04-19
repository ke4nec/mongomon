FROM python:2-alpine
MAINTAINER Liqin <ke4nec@qq.com>

ADD mongomon.tgz /
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.ustc.edu.cn/g' /etc/apk/repositories ; \
    apk update; apk add git ;\
#    git clone https://github.com/ke4nec/mongomon.git ;\
    cd /mongomon ;\
    pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade pip; \
    pip install -i https://pypi.tuna.tsinghua.edu.cn/simple PyYAML==5.1.1 pymongo requests; \
    mkdir /etc/cron.d && cp ./conf/mongomon_cron /etc/cron.d/ ;\
    crontab /etc/cron.d/mongomon_cron ; \
    apk del git ; \
    rm -rf /root/.cache;


WORKDIR /mongomon/bin
ENTRYPOINT ["crond", "start", "-f"]



