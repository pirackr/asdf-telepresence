# asdf-kubectl

[![CircleCI](https://circleci.com/gh/pirackr/asdf-telepresence/tree/main.svg?style=svg)](https://circleci.com/gh/pirackr/asdf-telepresence/tree/main)

Telepresence plugin for [asdf](https://github.com/asdf-vm/asdf) version manager. Forked from [Kubectl plugin](github.com/asdf-community/asdf-kubectl). 

## Install

```
asdf plugin-add kubectl https://github.com/pirackr/asdf-telepresence.git
```

## Use

Check out the [asdf documentation](https://asdf-vm.com/#/core-manage-versions?id=install-version) for instructions on how to install and manage versions of Kubectl.

## Architecture Override
The `ASDF_TELEPRESENCE_OVERWRITE_ARCH` variable can be used to override the architecture that is used for determining which `telepresence` build to download. The primary use case is when attempting to install an older version of `telepresence` for use on an Apple M1 computer as `telepresence` was not built for ARM at the time.

### Without `ASDF_TELEPRESENCE_OVERWRITE_ARCH`:

```
% asdf install telepresence 2.4.10 
Downloading telepresence from https://app.getambassador.io/download/tel2/linux/arm64/2.4.10/telepresence
```

### With `ASDF_TELEPRESENCE_OVERWRITE_ARCH`:

```
% ASDF_TELEPRESENCE_OVERWRITE_ARCH=amd64 asdf install kubectl 2.4.10
Downloading telepresence from https://app.getambassador.io/download/tel2/linux/amd64/2.4.10/telepresence
```

