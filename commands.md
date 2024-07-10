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
