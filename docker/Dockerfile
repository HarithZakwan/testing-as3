# docker/Dockerfile
FROM ubuntu:24.04

LABEL maintainer="<dadt01group15>"

ENV DEBIAN_FRONTEND=noninteractive
ENV TZ=Asia/Brunei

RUN apt-get update && \
    apt-get install -y curl zip unzip git nginx php8.3 php8.3-fpm php8.3-cli php8.3-mysql php8.3-xml \
    php8.3-mbstring php8.3-curl php8.3-bcmath php8.3-soap php8.3-intl php8.3-readline php8.3-zip php8.3-xdebug \
    supervisor composer tzdata redis && \
    echo "Asia/Brunei" > /etc/timezone && \
    ln -sf /usr/share/zoneinfo/Asia/Brunei /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata

WORKDIR /var/www/html

COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 80
CMD service php8.3-fpm start && service nginx start && tail -f /dev/null
