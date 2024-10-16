# Wiggle Tools

This repository provides tools for use with the [Wiggle library](https://github.com/dshills/wiggle), focusing on container management and vector database integrations. It houses the vector and container packages, designed to be lightweight, dependency-free solutions for handling operations in these areas.


![logo](https://raw.githubusercontent.com/dshills/wiggle/refs/heads/main/logo/wiggle_logo_512x512.png)

## Important Note

These package are internally written tools based on various vendor specifications specifically to be dependency free. You may want to consider using the vendor supplied SDKs to support more features as well as code that has been tested by the vendor and it's community.

## Packages

### vector

The vector package provides an abstraction for interacting with vector databases. It offers a flexible interface for working with multiple vector database backends, including Pinecone and Qdrant.

- Features:
    - Generic Vector interface to support multiple vector databases.
    - Implementations for popular vector databases like Pinecone and Qdrant.
    - Extensible for adding new vector database support with minimal effort.

### container

The container package offers a generic way to interact with containerization platforms such as Docker. It enables seamless container management, with support for starting, stopping, and waiting for containers.

- Features:
    - A unified interface for managing containers (Instance, Options).
	- Current implementation supports Docker, with future expansion to other container platforms.
	- No external dependencies, keeping the design lightweight and easy to integrate.

## Installation

To use the packages in this repository, install them via Go modules:

```sh
go get github.com/dshills/wiggle-tools/vector
go get github.com/dshills/wiggle-tools/container
```


## Usage

### Vector Database

```go
import "github.com/dshills/wiggle-tools/vector"
import "github.com/dshills/wiggle-tools/vector/pinecone"

// Example using Pinecone
client := pinecone.NewClient(apiKey, dataPlaneURL, controlPlaneURL)
vec := pinecone.NewVectorDB(client, "namespace")
// Interact with the vector database...
```

### Container Management

```go
import "github.com/dshills/wiggle-tools/container"
import "github.com/dshills/wiggle-tools/container/docker"

// Example using Docker
dock := docker.NewDocker()
instance, err := dock.StartContainer(image, options)
// Start, stop, and manage containers...
```

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests to enhance the functionality or support additional databases and container platforms.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
