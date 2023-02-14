FROM ubuntu:22.04

# Setting timezone to Montreal for PHP installation
ENV TZ=America/Montreal
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update \
    && apt-get -y install git software-properties-common wget unzip \
    && add-apt-repository ppa:ondrej/php \
    && apt install php8.2 php8.2-pgsql php8.2-bcmath php8.2-curl php8.2-mbstring php8.2-xml php8.2-zip -y

# Installing composer
RUN wget https://raw.githubusercontent.com/composer/getcomposer.org/76a7060ccb93902cd7576b67264ad91c8a2700e2/web/installer -O - -q | php -- --quiet
RUN mv composer.phar /usr/local/bin/composer