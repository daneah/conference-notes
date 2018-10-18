# "An Intro to Docker for Djangonauts" by Lacey Williams Henschel

## Terminology

* _Image_ - the "blueprint" of the application to be run
* _Container_ - a running instance of the application
* `Dockerfile` - The set of instructions used to create an image


## `Dockerfile`

1. `IMAGE` - the base image to use as the foundation for _your_ image
1. `PYTHONUNBUFFERED` and `PYTHONDONTWRITEBYTECODE`
1. Copy dependencies file and install
1. Copy application code
1. Command to run application


## Building

`$ docker build`

Use the `-t` flag to name the built image with a tag like `myapp:latest`.


## Layers

Images are based on other images which might be based on other images, etc.
Each step in a `Dockerfile` creates a layer of building.
Docker caches images and layers so that subsequent builds can go faster.
Changing an earlier layer invalidates all later layers.


## Running

`$ docker run -p 8000:8000 myapp:latest`

Runs a container from the `myapp:latest` image and forwards port `8000` in the container to port `8000` on your computer.

`$ docker container ls`

Shows running containers

`$ docker stop <container id>`

Stops a container (but keeps it around), which can be restarted later with `docker start`.

`$ docker kill <container id>`

Blitzes the container completely.


## Docker Compose

Allows you run and connect multiple containers at one time.
Uses a `docker-compose.yml` file to describe the pieces of the application to run.
Makes data volumes available so you can persist data separate from containers.

`$ docker-compose up`

Builds all the necessary images and starts the specified configuration of containers from `docker-compose.yml`.

`$ docker-compose down`

Take down the configuration

`$ docker-compose stop <service name>`

Stop a specific service in your configuration instead of the whole configuration.
