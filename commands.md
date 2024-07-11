# Docker Common Commands

- **Run a container from an image:**

```
docker run --interactive --tty --name my_container ubuntu:22:04
```

The flag `interactive OR -t` and `tty or -i` are used to keep the container running in the foreground so that you can interact with it. tty means terminal

The flag name is used to give the container a name.

- **List all containers:**

```
docker ps -a // to show all containers
docker ps // to only show all running containers

```

- **Restart a container and interact with it:**

```
docker start my_container // to start the container
docker attach my_container // to attach the shell process with this container so that it become interactive
```

- **Important flags**

1. -d: That means detech mode. It will run the container in the background
2. --entrypoint: To override the default entrypoint of the container
3. --env, -e, --env-file: To set environment variables
4. --interactive, -i, --ttym -t: To keep the container running in the foreground
5. --mount, --volume, -v: To mount a volume
6. --name: To give the container a name
7. --network, --net: To connect the container to a network, specifying this creates isolated network for the container rather than using the default docker network.
8. --platform: To specify the platform, which linux architecture to use
9. --publish, -p: To publish a container's port(s) to the host
10. --restart: To specify a restart policy
11. --rm: To remove the container when it stops

- **Networking Commands**

  1. Create a network

  ```
      docker network create my_network
  ```

  2. List all networks

  ```
      docker network ls
  ```

  3. Inspect a network

  ```
      docker network inspect my_network
  ```

  4. Connect a container to a network

  ```
      docker network connect my_network my_container
  ```

- **Docker Compose Commands**

  1. Run docker compose build

  ```
    docker-compose build
  ```

  2. Run a docker-compose file

  ```
  docker-compose up
  ```

  3. stop docker compose

  ```
  docker-compose stop
  ```
