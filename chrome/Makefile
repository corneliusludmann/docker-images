run: start-docker setxhost
	docker-compose run --rm chrome

build: start-docker
	docker-compose build

start-docker:
	systemctl is-active --quiet docker || sudo systemctl start docker

setxhost:
	xhost +"local:docker@"

unsetxhost:
	xhost -"local:docker@"
