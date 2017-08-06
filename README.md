Traefik Getting started von Marco Paga ist lizenziert unter einer Creative Commons Namensnennung - Weitergabe unter gleichen Bedingungen 4.0 International Lizenz.

 Usage

$ docker-compose up -d
$ curl -L -H Host:whoami.docker.localhost http://localhost
$ docker-compose scale whoami=3
$ curl -L -H Host:whoami.docker.localhost http://localhost
$ curl -L -H Host:whoami.docker.localhost http://localhost
$ docker-compose down

