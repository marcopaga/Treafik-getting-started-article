
# Intro
This a the companion project for the [post](https://blog.codecentric.de/en/2017/09/traefik-modern-reverse-proxy/) on the codecentric blog. You can use it to follow along and setup your own environment to play with [Traefik](https://traefik.io/).
This project will create two virtual machines as a server and a client. The server will host a DNS server and a Traefik server. The client is configured to use the previously created DNS resolver.

# Setup

To get started make sure you have [Vagrant](https://www.vagrantup.com/) installed on your machine. Once you are ready to go you can set the environment up:

`vagrant up`

This will create the two virtual machines with the name server and client.

# Usage

Now you can test the configuration

`vagrant ssh client`

Now you work within the context of the test DNS Server and the demo Traefik instance.

Now you access the whoami docker container on the server

`curl whoami.server.test`  

# Configuration Files 

* [docker-compose-services.j2](provision/templates/docker-compose-services.j2)
* [docker-compose-traefik.j2](provision/templates/docker-compose-traefik.j2)
* [server-hostsfile.j2](provision/templates/server-hostsfile)
