FROM ubuntu:16.04 

ENV LC_ALL=C.UTF-8 

RUN apt-get update && apt-get install -y && \
    apt-get -y install python3 python3-pip curl wget youtube-dl && \
    pip3 install yle-dl

WORKDIR /ylevideos

ENTRYPOINT ["yle-dl"]