# Use an official PHP image as the base
FROM php:8.2-apache

# Install dependencies
RUN apt-get update && \
    apt-get install -y libicu-dev && \
    docker-php-ext-install intl

# Enable Apache mod_rewrite (if using Apache)
RUN a2enmod rewrite

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Set working directory
WORKDIR /var/www/html

# Expose port 80
EXPOSE 80
