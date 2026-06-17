FROM php:8.4.22-fpm-alpine

RUN apk add --no-cache \
    $PHPIZE_DEPS \
    && docker-php-ext-install \
        pdo \
        pdo_mysql \
        opcache \
    && docker-php-ext-enable opcache \
    # Cleanup build depts to keep image small
    && apk del $PHPIZE_DEPS

# OPCahce config (for production)
RUN { \
    echo "opcache.enable=1"; \
    echo "opcache.memory_consumption=256"; \
    echo "opcache.interned_strings_buffer=16"; \
    echo "opcache.max_accelerated_files=32531"; \
    echo "opcache.validate_timestamp=1"; \
    echo "opcache.revalidate_freq=0"; \
    echo "opcache.fast_shutdown=1"; \
} > /usr/local/etc/php/conf.d/opcache.ini

# Production PHP Config
RUN cp "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

WORKDIR /var/www/html

# takeover folder 
RUN chown -R www-data:www-data /var/www/html

# run as www-data (non-root)
USER www-data