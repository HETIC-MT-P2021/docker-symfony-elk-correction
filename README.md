# Docker Symfony ELK Correction

This repository contains a correction for the Docker ELK exercise.

It is not the only way to do it.

## Instructions

Have a symfony application that logs in ElasticSearch through LogStash, visualisation available on Kibana.
Everything have to be containerized using Docker and Docker-Compose.

## How to start

Run `docker-compose up -d` then `docker-compose exec php composer install` to install PHP dependencies.

You will find the application at [http://127.0.01:8080](http://127.0.01:8080) and kibana at [http://127.0.01:8081](http://127.0.01:8081)
