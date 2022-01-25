# asdf-kubectl

[![Build Status](https://travis-ci.org/asdf-community/asdf-kubectl.svg?branch=master)](https://travis-ci.org/pirackr/asdf-telepresence)

Telepresence plugin for [asdf](https://github.com/asdf-vm/asdf) version manager. Forked from [Kubectl plugin](github.com/asdf-community/asdf-kubectl). 

## Install

```
asdf plugin-add kubectl https://github.com/pirackr/asdf-telepresence.git
```

## Use

Check out the [asdf documentation](https://asdf-vm.com/#/core-manage-versions?id=install-version) for instructions on how to install and manage versions of Kubectl.

## Architecture Override
The `ASDF_KUBECTL_OVERWRITE_ARCH` variable can be used to override the architecture that is used for determining which `telepresence` build to download. The primary use case is when attempting to install an older version of `kubectl` for use on an Apple M1 computer as `kubectl` was not built for ARM at the time.

### Without `ASDF_KUBECTL_OVERWRITE_ARCH`:

```
% asdf install kubectl 1.18.17
Downloading kubectl from https://storage.googleapis.com/kubernetes-release/release/v1.18.17/bin/darwin/arm64/kubectl
```

### With `ASDF_KUBECTL_OVERWRITE_ARCH`:

```
% ASDF_KUBECTL_OVERWRITE_ARCH=amd64 asdf install kubectl 1.18.17
Downloading kubectl from https://storage.googleapis.com/kubernetes-release/release/v1.18.17/bin/darwin/amd64/kubectl
```

