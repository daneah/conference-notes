## grouponDotCi

* "Turns Jenkins into Travis CI"
* Acts as glue between Jenkins, GitHub, Docker
* No manual server environment setup
* Docker Compose
* Should always get clean environment when starting testing
* Docker Plugin for Jenkins -> point Jenkins at Docker or Docker Swarm
  Spins up new Docker container
* Version-controlled job configurations
* Separate Dockerfile for each ruby version to test against
* docker-compose.yml
