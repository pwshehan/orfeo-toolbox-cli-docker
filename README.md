# OTB Docker Setup

This project provides a **Docker Compose** configuration for running the **Orfeo Toolbox (OTB)** CLI inside a Docker container with a mounted volume for data persistence.

## Features

- Uses the official **OTB Docker image**.
- Mounts a local `data` folder to the `/data` directory inside the container.
- Provides an interactive shell to execute OTB commands.

## Setup Instructions

### 1. Clone the Repository

```sh
git clone https://github.com/pwshehan/orfeo-toolbox-cli-docker.git
cd orfeo-toolbox-cli-docker
```

### 2. Create a `data` Directory

```sh
mkdir data
```

### 3. Start the OTB Container

```sh
docker-compose up -d
```

### 4. Access the Container

```sh
docker exec -it otb_container /bin/bash
```

### 5. Run an OTB Command

Example: Apply a simple band math operation to an image inside `./data`:

```sh
docker exec otb_container otbcli_BandMath -il /data/image.tif -out /data/result.tif -exp "im1b1 * 2"
```

## Stopping and Removing the Container

To stop the container:

```sh
docker-compose down
```

## Persistent Data

All processed images will be saved in the `./data` folder on your local machine.

## License

This project is open-source and available under the MIT License.
