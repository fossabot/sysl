# Sysl

[![GitHub Actions Go-Darwin status](https://github.com/anz-bank/sysl/workflows/Go-Darwin/badge.svg)](.)
[![GitHub Actions Go-Linux status](https://github.com/anz-bank/sysl/workflows/Go-Linux/badge.svg)](.)
[![GitHub Actions node-linux status](https://github.com/anz-bank/sysl/workflows/node-linux/badge.svg)](.)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FChloePlanet%2Fsysl.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FChloePlanet%2Fsysl?ref=badge_shield)


[![AppVeyor build](https://img.shields.io/appveyor/ci/anz-bank/sysl/master.svg?logo=appveyor)](https://ci.appveyor.com/project/anz-bank/sysl/branch/master)
[![Codecov](https://img.shields.io/codecov/c/github/anz-bank/sysl/master.svg)](https://codecov.io/gh/anz-bank/sysl/branch/master)
[![Gitter](https://img.shields.io/gitter/room/nwjs/nw.js.svg)](https://gitter.im/anz-bank/sysl)

Sysl (pronounced "sizzle") is a system specification language. Using Sysl, you
can specify systems, endpoints, endpoint behaviour, data models and data
transformations. The Sysl compiler automatically generates sequence diagrams,
integrations, and other views. It also offers a range of code generation
options, all from one common Sysl specification.

The set of outputs is open-ended and allows for your own extensions. Sysl has
been created with extensibility in mind and it will grow to support other
representations over time.

## Installation

With go get:

`go get -u github.com/anz-bank/sysl/cmd/sysl`


Sysl depends upon [PlantUML](http://plantuml.com/) for diagram generation. Some
of the automated tests require a PlantUML dependency. Provide PlantUML access
either via local installation or URL to remote service. Warning, for sensitive
data the public service at www.plantuml.com is not suitable. You can use one of
the following options to set up your environment:

- execute `SYSL_PLANTUML=http://www.plantuml.com/plantuml`
- add `export SYSL_PLANTUML=http://www.plantuml.com/plantuml` to your `.bashrc`
  or similar
- [install PlantUML](http://plantuml.com/starting) locally and run on port
  8080 or you can refer to the [plantuml server guide](docs/plantUML_server.md)

Test and lint the source code and your changes with

We encourage contributions to this project! Please have a look at the
[contributing guide](CONTRIBUTING.md) for more information.

If you need to create a release follow the [release
documentation](docs/releasing.md).


## Extending Sysl

In order to easily reuse and extend Sysl across systems, the Sysl compiler
translates Sysl files into an intermediate representation expressed as protocol
buffer messages. These protobuf messages can be consumed in your favorite
programming language and transformed to your desired output. In this way you are
creating your own Sysl exporter.

Using the [protoc compiler](https://developers.google.com/protocol-buffers/) you
can translate the definition file of the intermediate representation
`pkg/proto/sysl.proto` into your preferred programming language in a one-off
step or on every build. You can then easily consume Sysl models in your
programming language of choice in a typesafe way without having to write a ton
of mapping boilerplate. With that you can create your own tailored output
diagrams, source code, views, integrations or other desired outputs.

## Status

Sysl is currently targeted at early adopters. The current focus is to improve
documentation and usability, especially error messages and warnings.


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FChloePlanet%2Fsysl.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2FChloePlanet%2Fsysl?ref=badge_large)