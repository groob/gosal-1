# Gosal (sal-client)

*Gosal is an alpha project, and should not be considered for production use at this time.  There is no support, pull requests accepted :)*

## Overview

Gosal is intended to be a multi platform client for sal.

## Getting Started

Currently gosal uses a `LoadConfig` function that accepts a path to a to json file. This json file should be named `config.json` and located at the absolute path to the gosal.exe executable. Use the following format:

```json
{
  "key": "your gigantic machine group key",
  "url": "https://urltoyourserver.com/",
  "management": {
  "tool": "puppet",
  "path": "C:\\Program Files\\Puppet Labs\\Puppet\\bin\\puppet.bat",
  "command": "facts"
  }
}

```

# Building

To build the project after cloning:

```
make deps
make build
```

New macOS and windows binaries will be added to the `build/` directory.

## Dependencies

Gosal uses [dep](https://github.com/golang/dep#current-status) to manage external dependencies. Run `make deps` to install/update the required dependencies.
After adding a new dependency, run `dep ensure -update`, which will update the Gopkg.lock file. See [Adding a dependency](https://github.com/golang/dep#adding-a-dependency) for more.

## Formatting your code

Go has an exceptional formatter - please use it!
```
gofmt -s -w *.go
gofmt -s -w ./*/*.go
```
