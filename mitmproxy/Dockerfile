#FROM python:2
FROM ubuntu:12.04

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -q -y language-pack-en vim python-pip python-dev libffi-dev libxml2-dev libxslt1-dev && apt-get -q -y autoremove && apt-get clean && rm -rf /var/lib/apt/lists/* &&  update-locale LANG=en_US.UTF-8

RUN pip install mitmproxy

EXPOSE 8080

WORKDIR /

ENV LANG en_US.UTF-8

# docker run -it -v `pwd`:/source ipedrazas/silent mitmproxy -r /source/mitm-output.txt
# docker run -it -p 8080:8080  ipedrazas/silent mitmproxy -T
