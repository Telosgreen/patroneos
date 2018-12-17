FROM golang:stretch as builder

FROM haproxy:1.8

RUN apt update && apt install -y iptables && rm -rf /var/lib/apt/lists/* 

# Shell script to start HAProxy
COPY docker/proxy/start.sh /start.sh

# HAProxy
COPY docker/proxy/haproxy/haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg

EXPOSE 8082/tcp

USER root

CMD ["/start.sh"]
