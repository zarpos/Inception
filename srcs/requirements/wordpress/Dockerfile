FROM	debian:bookworm

RUN	mkdir -p /run/php

RUN	apt-get update && apt-get install -y php php-mysqli php-fpm wget mariadb-client

COPY	/tools/www.conf /etc/php/*/fpm/pool.d

RUN	wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar && chmod +x wp-cli.phar && mv wp-cli.phar /usr/local/bin/wp

COPY	/tools/configure.sh .

RUN	chmod 777 configure.sh

CMD	["./configure.sh"]
