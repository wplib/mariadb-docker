```
 __          _______  _      _ _       ____
 \ \        / /  __ \| |    (_) |     |  _ \
  \ \  /\  / /| |__) | |     _| |__   | |_) | _____  __
   \ \/  \/ / |  ___/| |    | | '_ \  |  _ < / _ \ \/ /
    \  /\  /  | |    | |____| | |_) | | |_) | (_) >  <
     \/  \/   |_|    |______|_|_.__/  |____/ \___/_/\_\
```

![WPLib-Box](https://github.com/wplib/wplib.github.io/raw/master/WPLib-Box-100x.png)


# MariaDB Docker Container for WPLib Box
This is the repository for the [mariadb-docker](https://www.mariadb.com/) Docker container implemented for [WPLib-Box](https://github.com/wplib/wplib-box).
It currently provides versions 5.5.59 10.0.34 10.1.31 10.2.13 10.3.4


## Supported tags and respective Dockerfiles

`10.3.4`, `10.3` _([10.3.4/Dockerfile](https://github.com/wplib/mariadb-docker/blob/master/10.3.4/Dockerfile))_

`10.2.13`, `10.2`, `latest` _([10.2.13/Dockerfile](https://github.com/wplib/mariadb-docker/blob/master/10.2.13/Dockerfile))_

`10.1.31`, `10.1` _([10.1.31/Dockerfile](https://github.com/wplib/mariadb-docker/blob/master/10.1.31/Dockerfile))_

`10.0.34`, `10.0` _([10.0.34/Dockerfile](https://github.com/wplib/mariadb-docker/blob/master/10.0.34/Dockerfile))_

`5.5.59`, `5.5` _([5.5.59/Dockerfile](https://github.com/wplib/mariadb-docker/blob/master/5.5.59/Dockerfile))_


## Using this container.
If you want to use this container as part of WPLib, then use the Docker Hub method.
Or you can use the GitHub method to build and run the container.


## Using it from Docker Hub

### Links
(Docker Hub repo)[https://hub.docker.com/r/wplib/mariadb/]

(Docker Cloud repo)[https://cloud.docker.com/swarm/wplib/repository/docker/wplib/mariadb/]


### Setup from Docker Hub
A simple `docker pull wplib/mariadb` will pull down the latest version.


### Runtime from Docker Hub
start - Spin up a Docker container with the correct runtime configs.

`docker run -d --name wplib_mariadb_10.3.4 --restart unless-stopped --network wplibbox -p 3306:3306 -v /vagrant/sql:/docker-entrypoint-initdb.d -v mariadb_data:/var/lib/mariadb wplib/mariadb:10.3.4`

stop - Stop a Docker container.

`docker stop wplib_mariadb_10.3.4`

run - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.

`docker run --rm --name wplib_mariadb_10.3.4 --network wplibbox -p 3306:3306 -v /vagrant/sql:/docker-entrypoint-initdb.d -v mariadb_data:/var/lib/mariadb wplib/mariadb:10.3.4`

shell - Run a shell, (/bin/bash), within a Docker container.

`docker run --rm --name wplib_mariadb_10.3.4 -i -t --network wplibbox -p 3306:3306 -v /vagrant/sql:/docker-entrypoint-initdb.d -v mariadb_data:/var/lib/mariadb wplib/mariadb:10.3.4 /bin/bash`

rm - Remove the Docker container.

`docker container rm wplib_mariadb_10.3.4`


## Using it from GitHub repo

### Setup from GitHub repo
Simply clone this repository to your local machine

`git clone https://github.com/wplib/mariadb-docker.git`


### Building from GitHub repo
`make build` - Build Docker images. Build all versions from the base directory or specific versions from each directory.


`make list` - List already built Docker images. List all versions from the base directory or specific versions from each directory.


`make clean` - Remove already built Docker images. Remove all versions from the base directory or specific versions from each directory.


`make push` - Push already built Docker images to Docker Hub, (only for WPLib admins). Push all versions from the base directory or specific versions from each directory.


### Runtime from GitHub repo
When you `cd` into a version directory you can also perform a few more actions.

`make start` - Spin up a Docker container with the correct runtime configs.


`make stop` - Stop a Docker container.


`make run` - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.


`make shell` - Run a shell, (/bin/bash), within a Docker container.


`make rm` - Remove the Docker container.


`make test` - Will issue a `stop`, `rm`, `clean`, `build`, `create` and `start` on a Docker container.


