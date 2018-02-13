## Commands

* `docker version`: Prints client and server versions.
* `docker info`: Print advanced info about host.
* `docker run <image_name>`: Runs a new container.
    * `docker run -d --name web -p 80:8080 hello-world`
        * `-d`: Run in detached mode.
        * `--name web`: Give container a name. Must be unique.
        * `-p 80:8080`: Declare ports. Maps port 8080 on container to port 80 on host.
        * `hello-world`: Name of image or container id.
    * `docker run -it --name temp ubuntu:latest /bin/bash`
        * `-it`: Interactive terminal.
        * `/bin/bash`: Executable to run in container.
    * `docker run -v /var/www container`
        * `-v /var/www`: Create a volume inside container.
    * `docker run -v $(pwd):/var/www container`
        * `-v /var/www`: Create a volume mapping from working directory to container folder.
    * `docker run -d -p 5000:5000 --link my-postgres:postgres aspnetcore`
        * `--link <container_name>:<container_alias>`: Link container to another by name/alias.
    * `docker run -d --net=isolated_network -p 5000:5000 aspnetcore`
        * `--link <container_name>:<container_alias>`: Link container to another by name/alias.
* `docker ps`: List running containers.
    * `docker ps -a`: Show all containers even if they exited.
* `docker images`: Show all images installed locally.
* `docker pull <image_name>`: Download latest image from Docker Hub.
    * `docker pull <image_name>:3.0`: Download image version.
* `docker rmi <image_name>:<version>`: Remove installed image.
* `docker start`: Starts container by name/id.
* `docker stop`: Kills container by name/id.
* `docker rm`: Deletes container by name/id.
    * `docker rm -v <container>`: Removes container and clean volumes.
* `docker inspect`: Print JSON container details.
* `docker build`: Create image from Dockerfile.
    * `docker build -f Dockerfile -t daniel-lillja/node .`
        * `-f Dockerfile`: Specify build file.
        * `-t daniel-lillja/node`: Specify tag.
        * `.`: Build context is current directory.
* `docker push author/name`: Push an image to docker registry.
* `docker exec`: Execute command in container.
    * `docker exec d6 node start.js`: Execute commanad in d6 container.
* `docker network create --driver bridge isolated_network`
    * `docker network create`: Create custom network.
    * `bridge`: Use bridge network.
    * `isolated_network`: Network name.
* `docker network ls`: List networks.
* `docker network inspect isolated_network`: Get details for a network by name.
* `docker volume create --name testvol`: Create shared volume with name.