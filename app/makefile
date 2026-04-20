# mission_1 makefile 
# make build : to build a docker image 
# make test : to test the app inside the container
# make run : to run the app
# make lint : to check the docker file
# make clean : to stop and clean all the containers/images

build:
	docker compose build

run:
	docker compose up -d

test:
	docker compose run --rm web pytest

lint:
	docker compose run --rm web flake8 app tests

clean:
	docker compose down --rmi all --volumes --remove-orphans