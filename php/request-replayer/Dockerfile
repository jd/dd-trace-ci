FROM php:7.3

RUN apt-get update \
  && apt-get install -y git unzip \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www

RUN (curl -q https://raw.githubusercontent.com/composer/getcomposer.org/76a7060ccb93902cd7576b67264ad91c8a2700e2/web/installer | php -- --filename=composer --install-dir=/usr/local/bin);

COPY src /var/www

EXPOSE 80

RUN composer install

CMD [ "php", "-S", "0.0.0.0:80", "index.php" ]
