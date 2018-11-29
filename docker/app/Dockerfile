# Use php runtime alpine image
FROM php:7.2-alpine

# Setting up ENV variables
ENV APP_DIR="/app" \
    APP_PORT="80"

# Installing packages
RUN apk --no-cache add \
    libmcrypt-dev \
    icu-dev \
 && docker-php-ext-install \
    intl 
    #mcrypt \
    #pdo \
    #pdo_mysql

# Setup working directory
WORKDIR $APP_DIR

# copy working directory
COPY . $APP_DIR 

VOLUME $APP_DIR/storage

# Make port 80 available to the world outside this container
EXPOSE $APP_PORT

# Run these commands when container launches
CMD php artisan serve \
    --host=0.0.0.0 \
    --port=$APP_PORT 
