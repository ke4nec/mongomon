FROM python:alpine
RUN apk add git ;\
    git clone https://github.com/ke4nec/mongomon.git ;\
    cd /mongomon ;\
    pip install PyYAML pymongo requests ; \
    mkdir /etc/cron.d && cp ./conf/mongomon_cron /etc/cron.d/ ;\
    crontab /etc/cron.d/mongomon_cron ;

WORKDIR /mongomon/bin
ENTRYPOINT ["/bin/sh", "-c", "crond start"]


