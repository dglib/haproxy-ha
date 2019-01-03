FROM ubuntu:18.04

LABEL maintainer="shaker242@gmail.com"

ENV RUNLEVEL=1

RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y haproxy --no-install-recommends \
    && mkdir -p /run/haproxy \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD haproxy.conf /etc/haproxy/

CMD haproxy -f /etc/haproxy/haproxy.cfg