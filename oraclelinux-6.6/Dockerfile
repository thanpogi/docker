FROM oraclelinux:6.6
MAINTAINER https://github.com/thanpogi

ARG HTTP_PROXY_ARG=

ENV HOME=/root
ENV no_proxy="localhost, 192.168.*, 10.*, 127.0.*"
ENV http_proxy=$HTTP_PROXY_ARG
ENV https_proxy=$HTTP_PROXY_ARG
ENV HTTP_PROXY=$HTTP_PROXY_ARG
ENV HTTPS_PROXY=$HTTP_PROXY_ARG

WORKDIR ${HOME}

RUN \
	yum -y install tar && \
	yum -y install wget && \
	yum -y install gcc && \
	yum -y install openssl-devel && \

CMD ["/bin/bash"]