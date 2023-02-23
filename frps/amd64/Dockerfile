FROM amd64/alpine:3.15

ENV FRP_VERSION 0.47.0

RUN cd /root \
    &&  wget --no-check-certificate -c https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_amd64.tar.gz \
    &&  tar zxvf frp_${FRP_VERSION}_linux_amd64.tar.gz  \
    &&  cd frp_${FRP_VERSION}_linux_amd64/ \
    &&  cp frps /usr/bin/ \
    &&  mkdir -p /etc/frp \
    &&  cp frps.ini /etc/frp \
    &&  cd /root \
    &&  rm frp_${FRP_VERSION}_linux_amd64.tar.gz \
    &&  rm -rf frp_${FRP_VERSION}_linux_amd64/ 


EXPOSE 80
EXPOSE 443
EXPOSE 2000-3000
EXPOSE 2000-3000/udp
EXPOSE 7000-8000
EXPOSE 7000-8000/udp

ENTRYPOINT /usr/bin/frps -c /etc/frp/frps.ini