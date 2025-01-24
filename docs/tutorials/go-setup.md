# Setting Up A Dev Container For Go

* Primary author: [Sven Reyes](https://github.com/svenreyes)

!!! example ""
    **Welcome! In this tutorial, you'll learn how to create a new dev container for Go. By the end of this guide, you'll set up a Go development container (dev container) in Visual Studio Code (VS Code).** :smile:

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
    ```shell
    mkdir go-devcontainer
    cd go-devcontainer
    ```
    3. Initialize a Git repository:
    ```shell
    git init
    ```
2. Add a DevContainer
    1. Inside the `#!bash go-devcontainer` directory, create a folder named `.devcontainer`:
    ```shell
    mkdir .devcontainer
    ```
    2. Create a `devcontainer.json` file inside `.devcontainer`:
    ```shell
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

    !!! warning "Docker"
        Make sure Docker is running before reopening the project in a container.
    1. Open the folder in VSCode with `File > Open Folder`
    2. Reopen the project in a DevContainer:
        * Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on Mac) in VSCode.
        * Select **Remote-Containers: Reopen in Container**. This may take a few minutes while the image is downloaded and the requirements are installed.

4. Verify the Go Installation
    1. Open the terminal in VSCode (inside the container).
    2. Run the following command to verify the Go version:
    ```
    go version
    ```
    !!! note
        Use `#!go go version` to ensure a recent Go installation.
5. Set Up a Go Project
    1. Initialize a new Go module:
    ```go
    go mod init hello-comp423
    ```
    2. Create a new Go file named main.go:
    ```go
    touch main.go
    ```
6. Write the "Hello COMP423" Program
    Add the following code to main.go:
    ```go
    package main

    import "fmt"

    func main() {
        fmt.Println("Hello COMP423")
    }

    ```
7. Run the Program
    1. Run the program directly:
    ```go
    go run main.go
    ```
    The output should look like this:
    ```
    Hello COMP423
    ```
    2. Build the program:
    ```go
    go build -o hello-comp423
    ```
    3. Run the built binary:
    ```
    ./hello-comp423
    ```
!!! info
    * `#!go go run`: Compiles and executes the program directly without generating a binary.
    * `#!go go build`: Creates an executable binary that can be run independently.




