# pallet-example-exports
A simple "hello-world" Forklift pallet illustrating Forklift's file export feature

## Introduction

pallet-example-exports is a [Forklift](https://github.com/PlanktoScope/forklift) pallet
specifying an example set of Forklift packages and package deployments for a "hello world"-style
demonstration of file exports of systemd units to overlay into `/etc`. This pallet is structured as
a monorepo in which all packages to be deployed are also defined by the pallet (because it is also a
Forklift repository).

## Usage

### Prerequisites

You will need to set up the [`forklift`](https://github.com/PlanktoScope/forklift) tool on
your computer. Setup instructions are available
[here](https://github.com/PlanktoScope/forklift?tab=readme-ov-file#downloadinstall-forklift). Note
that currently `forklift` is only tested for Linux computers.

### Deployment

You can clone and stage the latest commit of this Forklift pallet to your computer acting, by
using the `forklift` tool:
```
forklift plt switch --no-cache-img github.com/ethanjli/pallet-example-exports@main
```

This pallet will create a new directory in `~/.local/share/forklift/stages`; you can determine the
path of that directory by running `forklift stage locate-bun next`. Inside that directory, the
`exports` subdirectory will be a file tree with files at
`overlays/etc/systemd/system/hello-world.service` and
`overlays/etc/systemd/system/multi-user.target.wants/hello-world.service`.
If you are running Forklift on a system (such as the PlanktoScope's software distribution) which
overlays the `exports/overlays/etc` subdirectory of the next staged Forklift pallet into `/etc`,
after you run the following commands:
```
sudo systemctl daemon-reload
sudo systemctl start hello-world.service
sudo systemctl status hello-world.service
```
you should see that `hello-world.service` ran and printed a hello-world message.

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
