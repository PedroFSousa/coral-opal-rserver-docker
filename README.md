# Opal R Server Docker

This repository contains the source code for building an [Opal R Server](http://opaldoc.obiba.org/en/latest/admin/rserver.html) Docker image based on the [original image from OBiBa](https://github.com/obiba/docker-opal-rserver).

## Building
After every commit, GitLab CI automatically builds the image and pushes it into INESC TEC's Docker Registry. The version tag of the image is determined from a string matching `##x.x.x##` on the commit message.

Alternatively, an image can be built locally by running:
`docker build -t opal-rserver-docker .`

**Volumes**  
To persist the data across executions, you can mount `/srv` as a volume.

## Running

Create a `docker-compose.yml` file (examples bellow) and run `docker-compuse up`.

```yml
version: '3.2'

services:
  opal:
    image: docker-registry.inesctec.pt/coral/coral-docker-images/coral-opal-rserver-docker:1.1.0
    container_name: rserver
    volumes:
    - rserver:/srv

volumes:
  rserver:
```

<br>

---
master: [![pipeline status](https://gitlab.inesctec.pt/coral/coral-docker-images/coral-opal-rserver-docker/badges/master/pipeline.svg)](https://gitlab.inesctec.pt/coral/coral-docker-images/coral-opal-rserver-docker/commits/master)

dev: &emsp;&ensp;[![pipeline status](https://gitlab.inesctec.pt/coral/coral-docker-images/coral-opal-rserver-docker/badges/dev/pipeline.svg)](https://gitlab.inesctec.pt/coral/coral-docker-images/coral-opal-rserver-docker/commits/dev)
