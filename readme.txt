mkdir /data/httpdApache
====================
index.html
====================
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8"/>
<title>Exemplo Apache com Docker-Compose</title>
</head>
<body>
<h1> OK !! Apache funcionando!!!!! </h1>
<h2> DOCKER COMPOSE </h2>
</body>
</html>
====================
mkdir /compose/httpdApache
====================
docker-compose.yml
====================

version: '3.7'

services:
  httpdApache:
    image: httpd

    ports:
      - "80:80"
    volumes:
      - /data/httpdApache:/usr/local/apache2/htdocs/
    networks:
      - minha-rede
networks: 
  minha-rede:
    driver: bridge



# docker-compose up -d

