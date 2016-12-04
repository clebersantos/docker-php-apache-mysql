# docker-php-apache-mysql
Docker com dois containeres com php+ apache e mysql, testando com Wordpress.

## acessar o container do mysql
  docker exec -it some-mysql bash
## configuracoes adicionais(colocar na imagem docker)

Adicionar e testar depois

RUN apt-get update \
&& apt-get install -y zlib1g-dev \
&& rm -rf /var/lib/apt/lists/* \
&& docker-php-ext-install zip

apt-get update
apt-get install php5-mysql vim libmcrypt-dev
docker-php-ext-install mysqli pdo pdo_mysql mcrypt
cp /usr/share/php5/php.ini-production /usr/local/etc/php/php.ini


## Ou
docker run -d -p 8080:80 --name my_web_app --link db:db -v "$PWD"/html:/var/www/html/ php:5.6-apache
