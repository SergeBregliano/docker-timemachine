# Docker - Timemachine

This docker-compose is based on the [Matt Bentley docker image](https://hub.docker.com/r/mbentley/timemachine) and designed to run a timemachine on a local server with a single user.



## Install

To make it run on your [Docker](https://www.docker.com/) install, you'll need to :

- Have [Docker Compose](https://docs.docker.com/compose/install/) running
- Clone [this repos](https://github.com/SergeBregliano/docker-timemachine) on the server
- Copy or rename the ``sample.env`` file in ``.env``
- Configure the ``.env`` file according to your needs

### .env configuration

Define the data path where your backup will be availables (must be formatted in ``ext4``).
```shell
DATA_PATH=./appData
```

Define the username and password pour the user
This stack only manage one user (see readme for more information)

```shell
USERNAME=Timemachine
PASSWORD=Timemachine
```

Define the container name. It can be whatever you want if the name is not already use in your Docker

```shell
CONTAINER_NAME=timemachine
```

Define the maximum size of the time machine backup. Units can be : K, M, G, T, P
```shell
VOLUME_SIZE_LIMIT=750G
```



### Updates

To update the stack according to the last version of this repos and the Doocker image, simply run the ``updateStack.sh`` file.

```shell
sudo sh ./updateStack.sh
```



## Warnings

- This stack run with **'host' network driver**
- This stack only manage a **single user**
- The Docker **image version is not fixed**, it use the latest one

You can do it different. Please refer to the [GitHub repos](https://github.com/mbentley/docker-timemachine) for more specifics usages.



## Thanks

Thanks to [Matt Bentley](https://www.mbentley.net/) for his good job, he saved me time !!

- Github : https://github.com/mbentley/docker-timemachine
- Docker image : https://hub.docker.com/r/mbentley/timemachine