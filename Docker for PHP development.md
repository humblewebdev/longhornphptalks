# Docker for PHP development
- Jessica Mauerhan
- [Talk Slides](https://joind.in/talk/cb9d6)
- Simple way to run docker
	- docker run
- docker hub is a registry for images
	- `docker images` gets available local images
- docker compose
	- used for networking containers
	- `docker-compose up -d`
		- D stands for detatched
- docker ps
	- shows all processes running
- docker-composer ps
	- lists containers
- overriding docker-compose config
	- docker-composer.override.yaml
		- can use for specific env configuration
- Mounting volumes locally for ephemeral use
	- 	docker volume create --name postgres-data -d local
	-  update docker compose file to use volumes
- volumes mounted to a container dont become part of the image.
- registering an image
- docker system prune -a
	- removes images not being used
- use docker machine in order to make the TDD process faster