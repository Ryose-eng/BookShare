FROM php:8.2-fpm

# Composer のインストール
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# 必要な PHP 拡張をインストール
RUN apt-get update && apt-get install -y \
    zip unzip git curl libpng-dev libonig-dev libxml2-dev \
    && docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd

# 作業ディレクトリを設定
WORKDIR /var/www/html
