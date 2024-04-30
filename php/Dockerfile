FROM php:8.3.0-fpm

RUN apt-get update -y
RUN docker-php-ext-install mysqli pdo pdo_mysql
RUN apt-get install -y wget
RUN ARCHITECTURE=$(uname -m) && \
    case "$ARCHITECTURE" in \
    x86_64) \
        wget https://github.com/evertiro/mhsendmail/releases/download/v0.2.0-M1/mhsendmail_linux_amd64 ;; \
    aarch64) \
        wget https://github.com/evertiro/mhsendmail/releases/download/v0.2.0-M1/mhsendmail_linux_arm64 ;; \
    *) \
        echo "Unsupported architecture" && exit 1 ;; \
    esac
RUN chmod +x mhsendmail_linux_*
RUN mv mhsendmail_linux_* /usr/local/bin/mhsendmail
RUN echo "sendmail_path = /usr/local/bin/mhsendmail --smtp-addr mailhog:1025" >> /usr/local/etc/php/conf.d/docker-fpm.ini


