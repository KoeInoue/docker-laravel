FROM node:10.17
RUN npm install -g gulp@3.9.1 gulp-phpunit config && \
    npm install gulp@3.9.1 gulp-phpunit config && \
    apt-get -y update && \
    apt-get -y upgrade && \
    apt-get -y install ca-certificates apt-transport-https && \
    wget -q https://packages.sury.org/php/apt.gpg -O- | apt-key add - && \
    echo "deb https://packages.sury.org/php/ stretch main" | tee /etc/apt/sources.list.d/php.list && \
    apt-get -y update && \
    apt-get -y install php7.4-readline && \
    apt-get -y install php7.4 php7.4-cli php7.4-common php7.4-opcache php7.4-curl php7.4-mbstring php7.4-mysql php7.4-zip php7.4-xml

WORKDIR /work/backend