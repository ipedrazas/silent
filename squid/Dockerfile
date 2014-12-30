FROM ubuntu:12.04
MAINTAINER ipedrazas@gmail.com

 RUN echo 'APT::Install-Recommends 0;' >> /etc/apt/apt.conf.d/01norecommends \
 && echo 'APT::Install-Suggests 0;' >> /etc/apt/apt.conf.d/01norecommends \
 && apt-get update \
 && apt-get install -y squid3 vim.tiny wget sudo net-tools ca-certificates \
 && mv /etc/squid3/squid.conf /etc/squid3/squid.conf.dist \
 && apt-get -q -y autoremove && apt-get clean && rm -rf /var/lib/apt/lists/*

ADD squid.conf /etc/squid3/squid.conf
ADD adservers.list /etc/squid3/blacklist

ADD start /start
RUN chmod 755 /start

EXPOSE 3128
VOLUME ["/var/spool/squid3"]

CMD ["/start"]
