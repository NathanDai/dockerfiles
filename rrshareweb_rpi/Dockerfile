FROM arm64v8/ubuntu
LABEL MAINTAINER="daizheng@dashwood.xyz"
RUN apt update \
        && apt install wget tzdata -y \
        && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
        && echo 'Asia/Shanghai' >  /etc/timezone \
        && mkdir -p /rrshare \
        && mkdir -p /opt/work/rrshareweb/data \
        && wget -q http://appdown.rrys.tv/rrshareweb_rpi.2.20.tar.gz -O /rrshare/rrshareweb_rpi.2.20.tar.gz \
        && tar -zxvf /rrshare/rrshareweb_rpi.2.20.tar.gz -C /rrshare/ \
        && rm -rf /rrshare/rrshareweb_rpi.2.20.tar.gz \
        && apt purge wget -y \
        && apt autoremove -y

WORKDIR /
VOLUME ["/opt/work/rrshareweb/data"]
EXPOSE 3001 

CMD ["sh", "-c", "/rrshare/rrshareweb_rpi/rrshareweb"]