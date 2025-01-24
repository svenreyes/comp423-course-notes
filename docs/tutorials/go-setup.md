# Setting Up A Dev Container For Go

* Primary author: [Sven Reyes](https://github.com/svenreyes)

Welcome! In this tutorial, you'll learn how to create a new dev container for Go. By the end of this guide, you'll set up a Go development container (dev container) in Visual Studio Code (VS Code). :smile:

## Prerequisites

Ensure you have the following installed on your system:

* [GitHub account](https://github.com/)
* [Visual Studio Code (VSCode)](https://code.visualstudio.com/)
* [Docker](https://www.docker.com/)
* [Git](https://git-scm.com/)

Install the VSCode extensions:

* Remote - Containers
* Go (by the Go Team at Google)

## Step-by-Step Instructions
1. Create a Blank Directory
    1. Open your terminal.
    2. Create a new directory for your project:
    ```bash
    mkdir go-devcontainer
    cd go-devcontainer
    ```
    3. Initialize a Git repository:
    ```bash
    git init
    ```
2. Add a DevContainer
    1. Inside the `#!bash go-devcontainer` directory, create a folder named `.devcontainer`:
    ```bash
    mkdir .devcontainer
    ```
    2. Create a `devcontainer.json` file inside `.devcontainer`:
    ```bash
    touch .devcontainer/devcontainer.json
    ```
    3. Add the following configuration to `devcontainer.json`:
    ```json
    {
        "name": "Go DevContainer",
        "image": "mcr.microsoft.com/devcontainers/go:0-1.19",
        "settings": {
            "go.toolsManagement.autoUpdate": true
        },
        "extensions": [
            "golang.go"
        ]
    }
    ```
3. Start the DevContainer
    1. Open the folder in VSCode with `File > Open Folder`
    2. Reopen the project in a DevContainer:
        * Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac) in VSCode.
        * Select **Remote-Containers: Reopen in Container**. This may take a few minutes while the image is downloaded and the requirements are installed.



