# pallet-example-sysexts
A Forklift pallet demonstrating the use of Forklift to manage systemd system extensions

## Introduction

pallet-example-sysexts is a [Forklift](https://github.com/PlanktoScope/forklift) pallet
specifying an example set of Forklift packages and package deployments for a deep demonstration of
a variety of different kinds of file exports of
[systemd sysexts/confexts](https://www.freedesktop.org/software/systemd/man/latest/systemd-sysext.html)
to overlay into the OS.

For simplicity, this pallet is structured as a monorepo in which all packages to be deployed are
also defined by the pallet (because this Git repo is declared as both a Forklift pallet and a
Forklift package repository).

## Usage

This pallet is meant to be used together with
[ethanjli/ublue-forklift-sysext-demo](https://github.com/ethanjli/ublue-forklift-sysext-demo)
as the host OS; for a step-by-step demonstration of the usage of this pallet, follow the
[usage guide of ethanjli/ublue-forklift-sysext-demo](https://github.com/ethanjli/ublue-forklift-sysext-demo/?tab=readme-ov-file#usage).

### Forking

To make your own copy of this repository for experimentation, you should fork this repository to a
new repository. Then, update the `path` fields of the `forklift-pallet.yml` and
`forklift-repository.yml` files to match the path of your new repository.

## Licensing

Forklift packages deployed by this pallet have their own software licenses, as specified in the
definitions of those packages. Any source code provided with this Forklift pallet is covered by the
following information, except where otherwise indicated:

Copyright Ethan Li and Forklift project contributors

SPDX-License-Identifier: Apache-2.0 OR BlueOak-1.0.0

You can use the source code provided here either under the
[Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0)
or under the [Blue Oak Model License 1.0.0](https://blueoakcouncil.org/license/1.0.0);
you get to decide. We are making the software available under the Apache license because it's
[OSI-approved](https://writing.kemitchell.com/2019/05/05/Rely-on-OSI.html),
but we like the Blue Oak Model License more because it's easier to read and understand.
