# To build and Run a docker container

  ## Build
    docker build -t <container-name>
  ## Run 
    docker run -dp port:port gett

# To Remove a container

1 - List running containers:
  docker ps

2 - To Stop a container:
  docker stop <the-container-id>

3 - To Remove a container:
  docker rm <the-container-id>


# To create a volume:

  docker volume create <volume-name>
  
  # Run docker w/ volume:
    docker run -dp port:port -v <volume-name>:<path-to-store-volume> <container-name>
    ex: docker run -dp 3000:3000 -v todo-db:/etc/todos getting-started


# Container Network
  Allow one container to talk to another.

  Note: If two containers are on the same network, they can talk to each other. If they aren't, they can't.

# Create a Network
  docker network create <network-name>

# create mysql database inside a network
  docker run -d \
     --network <network-name> --network-alias mysql \
     -v <volume-name>:/var/lib/mysql \
     -e MYSQL_ROOT_PASSWORD=<password> \
     -e MYSQL_DATABASE=<database> \
     mysql:5.7