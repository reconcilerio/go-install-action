# go-install action  <!-- omit in toc -->

[![CI](https://github.com/reconcilerio/go-install-action/actions/workflows/ci.yaml/badge.svg)](https://github.com/reconcilerio/go-install-action/actions/workflows/ci.yaml)

Install a go package at the requested version.

- [Usage](#usage)
- [Community](#community)
  - [Code of Conduct](#code-of-conduct)
  - [Communication](#communication)
  - [Contributing](#contributing)
- [License](#license)

## Usage

See [action.yml](action.yml)

<!-- start usage -->
```yaml
- uses: reconcilerio/go-install-action@v1
  with:
    # Required package.
    # The go package to install.
    # Default: ''
    package: ''
    # Optional version.
    # The go module's version to install.
    # Default: none
    version: ''
    # Optional toolchain.
    # The go toolchain to use.
    # Default: `${GOTOOLCHAIN}`
    version: ''
    # Optional working-directory.
    # directory containing a go.mod file defining the package's version
    # Default: ''
    working-directory: ''
    # Optional output.
    # Name of the built binary.
    # Default: none
    output: ''
    # Optional output-dir.
    # Directory to place the built binary. Defaults to `${GOBIN}` or `${GOPATH}/bin`.
    # Default: none
    output-dir: ''
    # Optional output-path-env.
    # Environment variable to set the output path to.
    # Default: none
    output-path-env: ''
    # Optional cache-enabled.
    # Cache built artifacts. If false, always build from source.
    # Default: 'true'
    cache-enabled: ''
```
<!-- end usage -->

**Basic:**

```yaml
steps:
- uses: reconcilerio/go-install-action@v1
  with:
    package: github.com/google/go-containerregistry/cmd/crane
    output-dir: /usr/local/bin
- run: crane ls ubuntu
```

When building from source, an appropriate go toolchain is required. If unsure, favor a more recent toolchain version.

## Community

### Code of Conduct

The reconciler.io projects follow the [Contributor Covenant Code of Conduct](./CODE_OF_CONDUCT.md). In short, be kind and treat others with respect.

### Communication

General discussion and questions about the project can occur either on the Kubernetes Slack [#reconcilerio](https://kubernetes.slack.com/archives/C07J5G9NDHR) channel, or in the project's [GitHub discussions](https://github.com/orgs/reconcilerio/discussions). Use the channel you find most comfortable.

### Contributing

The reconciler.io project team welcomes contributions from the community. A contributor license agreement (CLA) is not required. You own full rights to your contribution and agree to license the work to the community under the Apache License v2.0, via a [Developer Certificate of Origin (DCO)](https://developercertificate.org). For more detailed information, refer to [CONTRIBUTING.md](CONTRIBUTING.md).

## License

Apache License v2.0: see [LICENSE](./LICENSE) for details.
