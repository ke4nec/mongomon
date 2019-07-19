FROM python:alpine
RUN apk add git ;\
    git clone https://github.com/ke4nec/mongomon.git ;\
    cd /mongomon ;\
    pip install PyYAML pymongo requests ;
WORKDIR /mongomon/bin
ENTRYPOINT ["/bin/sh"]


