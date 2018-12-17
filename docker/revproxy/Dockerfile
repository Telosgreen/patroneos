FROM golang:stretch as builder

FROM haproxy:1.8

RUN apt update && apt install -y iptables && rm -rf /var/lib/apt/lists/* 

# Shell script to start HAProxy
COPY docker/revproxy/start.sh /start.sh
RUN chmod +x /start.sh

# HAProxy
COPY docker/revproxy/haproxy/haproxy.cfg /usr/local/etc/haproxy/haproxy.cfg
RUN touch fake.log

EXPOSE 8082/tcp

USER root

#CMD ["/start.sh"]
