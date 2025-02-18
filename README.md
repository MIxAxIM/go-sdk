<p align="center">
  <a href="https://www.gomaestro.org/">
    <img src="https://www.gomaestro.org/logos/LandingLogos/DarkLogo.svg" alt="Maestro Logo" width="425" />
  </a>
  <h2 align="center">Go SDK for the <a href="https://www.gomaestro.org/">Maestro</a> Dapp Platform</h2>
  <p align="center">
    <a href="https://docs.gomaestro.org/docs/intro">
      <img src="https://img.shields.io/badge/-Docs-blue?style=flat-square&logo=semantic-scholar&logoColor=white" />
    </a>
    <a href="https://github.com/maestro-org/go-sdk/blob/main/LICENSE">
      <img src="https://img.shields.io/github/license/maestro-org/go-sdk?style=flat-square&label=License" />
    </a>
    <a href="https://github.com/maestro-org/go-sdk/actions/workflows/main.yml?query=branch%3Amain">
      <img src="https://img.shields.io/github/actions/workflow/status/maestro-org/go-sdk/main.yml?style=flat-square&branch=main&label=Build" />
    </a>
    <a href="./CONTRIBUTING.md">
      <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square" />
    </a>
    <a href="https://twitter.com/GoMaestroOrg">
      <img src="https://img.shields.io/badge/-%40GoMaestroOrg-F3F1EF?style=flat-square&logo=twitter&logoColor=1D9BF0" />
    </a>
    <a href="https://discord.gg/ES2rDhBJt3">
      <img src="https://img.shields.io/badge/-Discord-414EEC?style=flat-square&logo=discord&logoColor=white" />
    </a>
    <a href="https://pkg.go.dev/github.com/maestro-org/go-sdk">
      <img src="https://pkg.go.dev/badge/golang.org/x/pkgsite.svg" />
    </a>
  </p>
</p>

# Getting Started

## Prerequisites
* Go 1.20
* [golangci-lint](https://golangci-lint.run/usage/install/) for linting
* [golines](https://github.com/segmentio/golines) for formatting

## Installation

### [Go Reference](https://pkg.go.dev/github.com/maestro-org/go-sdk#section-readme)

```bash
go get -u github.com/maestro-org/go-sdk@main
```

## Usage

```go
import "github.com/maestro-org/go-sdk/client"

maestroClient := client.NewClient("<PROJECT_API_KEY>", "<NETWORK>")
```

* To generate an API key, create a free account [here](https://dashboard.gomaestro.org/)!
* Network options: `preview`, `preprod`, `mainnet`, `sanchonet`

## Example

```go
package main

import (
	"fmt"

	"github.com/maestro-org/go-sdk/client"
)

func main() {
	maestroClient := client.NewClient("<PROJECT_API_KEY>", "mainnet")
	blockInfo, err := maestroClient.BlockInfo(9005859)
	if err != nil {
		fmt.Printf("Failed to retrieve block info: %s\n", err)
	}
	fmt.Println(blockInfo.Data.AbsoluteSlot)
}
```

# Documentation

* [Maestro public docs](https://docs.gomaestro.org/)

# Contributing
Meastro welcomes all contributors! Please see our [contributing guidelines](CONTRIBUTING.md) and [code of conduct](CODE_OF_CONDUCT.md).
