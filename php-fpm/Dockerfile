FROM php:8.1-fpm

# 必要な拡張をインストール
RUN apt-get update \
  && apt-get install -y libzip-dev zip \
  && docker-php-ext-install mysqli pdo_mysql zip \
  && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www/html

# 権限調整（ホストOSに合わせて調整）
RUN chown -R www-data:www-data /var/www/html
