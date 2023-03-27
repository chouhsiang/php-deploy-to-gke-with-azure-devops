FROM composer as builder
WORKDIR /app/
COPY composer.* ./
RUN composer install

FROM php:8.2-apache
COPY . /var/www/
COPY --from=builder /app/vendor /var/www/vendor
RUN rm -rf /var/www/html && ln -s /var/www/public /var/www/html
