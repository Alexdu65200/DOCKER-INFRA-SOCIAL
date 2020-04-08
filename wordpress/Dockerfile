FROM wordpress:fpm-alpine

COPY ./wp-cli.phar /home
RUN chmod +x /home/wp-cli.phar
RUN mv /home/wp-cli.phar /usr/local/bin/wp

RUN echo "exec php-fpm"
CMD wp core install --url=${ADMIN_DOMAIN} --title=Example --admin_user=test --admin_password=test --admin_email=Alexdu65200@gmail.com --allow-root && wp plugin install multiple-domain --allow-root --activate && exec php-fpm