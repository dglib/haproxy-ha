FROM ubuntu:18.04

LABEL maintainer="shaker242@gmail.com"

ENV RUNLEVEL=1

RUN apt-get update \
    && apt-get upgrade -y \
    && apt-get install -y heartbeat --no-install-recommends \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

ADD ha.d/* /etc/ha.d/
RUN echo "net.ipv4.ip_nonlocal_bind=1" >> /etc/sysctl.conf \
    && chmod 440 /etc/ha.d/authkeys

CMD 