# Docker devContainer

**Docker Development Environment**

This repository contains a Dockerfile for setting up a Docker development environment using Docker-in-Docker (DinD). It is designed to facilitate the building and management of Docker containers from within a devcontainer, providing a consistent and isolated development environment.

## Features

- **Docker-in-Docker**: Utilizes the Docker DinD image to enable Docker operations within the container.
- **Reproducibility**: All essential tools and packages are pinned by version to ensure that the environment is consistent and reproducible across different setups.
- **Non-root User**: Runs as a non-root user by default to enhance security.
- **Health Checks**: Includes a health check to ensure the Docker daemon is running correctly within the container.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your host machine.
- [Visual Studio Code](https://code.visualstudio.com/) with the [Remote - Containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed.

## Setup and Usage

1. **Clone this Repository**

   ```bash
   git clone https://github.com/kockums/docker-devcontainer.git
   cd docker-dev-environment
   ```

2. **Reopen in Container**
   - Open the project in Visual Studio Code.
   - VS Code may prompt you to reopen in a container. If not, press `F1` or `Ctrl+Shift+P`, type "Reopen in Container", and execute the command.

3. **Start Building Docker Images**
   - Use standard Docker commands within the container to build, run, and manage your Docker images and containers.

## Customization

You can customize the Docker development environment by modifying the `Dockerfile` and `devcontainer.json`:

- Update the versions in the Dockerfile using build arguments to test different tool versions.
- Modify `devcontainer.json` to change settings or add extensions as needed for your development workflow.

## Contributing

Contributions to this repository are welcome. Please fork the repository and submit a pull request with your changes.

## License

Distributed under the MIT License. See `LICENSE` for more information.
