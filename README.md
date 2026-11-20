# openfaas-cloud

OpenFaaS Cloud automates the work between a source-control push and a deployed OpenFaaS function. It gives teams a shared platform where users can build, deploy, and monitor functions from their GitHub or GitLab workflows.

## Features

- **Build functions** from GitHub or GitLab push events.
- Clone source repositories, build Docker images with BuildKit, and push images to a registry.
- Deploy functions to a Kubernetes or Docker Swarm OpenFaaS cluster.
- Provide each user with a dashboard for viewing functions and runtime logs.
- Report build and deployment status through GitHub Checks or GitLab Statuses.
- Route users or organizations through subdomains with HTTPS.

## Installation

Install the project with Go:

```sh
go install github.com/openfaas/openfaas-cloud@latest
```

To build from source instead:

```sh
git clone https://github.com/openfaas/openfaas-cloud.git
cd openfaas-cloud
go build ./...
```

A complete self-hosted installation also requires an OpenFaaS cluster, a domain name, a public IP or an equivalent ingress setup, and configuration for your GitHub or GitLab integration. The `ofc-bootstrap` project can automate a Kubernetes installation with authentication and wildcard certificates.

## Usage

After installation, inspect the available commands and configuration options with:

```sh
openfaas-cloud --help
```

A local development invocation can use a configuration file when supported by the built binary:

```sh
openfaas-cloud --config ./config.yaml
```

The deployed workflow receives a Git push event, clones the repository, builds and publishes the function image, then deploys the function to the configured OpenFaaS cluster. Users can check status and runtime logs in their personal dashboard.

## License

This project is licensed under the MIT License. It is based on [openfaas/openfaas-cloud](https://github.com/openfaas/openfaas-cloud), which is also licensed under MIT. See the `LICENSE` file for the full license text.

