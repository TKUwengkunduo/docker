# Docker

## Introduction

This project provides a Docker containerized environment, including necessary configuration files and scripts, to help users quickly start and run the project. Please follow the steps below to set up and use it.

## Download the Project

Clone the project to your local workspace using Git:

```bash
git clone https://github.com/TKUwengkunduo/docker.git
cd docker
```

## File Permissions

Ensure the scripts are executable by running the following commands:

```bash
chmod +x build.sh
chmod +x run.sh
```

## Build Docker Image

Use the provided Dockerfile to build the Docker image. By default, the image name is `custom_image`, but you can specify a custom name during the build process.

### Build Docker Image

Run the following command to build the image:

```bash
./build.sh
```

### Customize Image Name

If you need to modify the image name, edit `build.sh`, locate the following line, and replace it:

```bash
IMAGE_NAME="my_image"  # Replace my_image with your desired name
```

## Run Container

The run script will start the container. The default image name is `yolo`. You can start it with the following command:

```bash
./run.sh
```

To modify the image name, edit `run.sh`, locate the following line, and replace it:

```bash
IMAGE_NAME="my_image"  # Replace my_image with your desired image name
```

## Modify Configuration File

The project provides a `tmux.conf` file with the following settings:

- Enable mouse mode: `set -g mouse on`
- Shortcut keys for splitting panes:
  - Ctrl+H for horizontal split: `bind -n C-h split-window -h`
  - Ctrl+V for vertical split: `bind -n C-v split-window -v`

To customize, directly modify the `tmux.conf` file and restart tmux to apply changes.

## Appendix

### Check Running Containers

Use the following command to check for running containers:

```bash
docker ps
```

### Stop a Container

Use the following command to stop a running container:

```bash
docker stop <container_name>
```

### Remove a Container

To remove a container, use:

```bash
docker rm <container_name>
```

### Remove an Image

To delete an image, use the following command:

```bash
docker rmi <image_name>
```


