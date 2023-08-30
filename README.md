# RPMbuild action

A GitHub action to build an RPM.

## Inputs

### `distribution`

The distribution to run on. Currently supported: (selection not working)

- [`rockylinux-8`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/rockylinux-8) (default)
- [`centos-8`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/centos-8) (defunct)
- [`centos-7`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/centos-7)
- [`fedora-37`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/fedora-37)
- [`fedora-34`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/fedora-34)
- [`fedora-33`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/fedora-33)
- [`fedora-32`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/fedora-32)
- [`fedora-31`](https://github.com/robertdebock/docker-github-action-rpmbuild/tree/fedora-31)

## Requirements

This action expects the following structure:

```
.
├── README.md
├── SOURCES
│   └── my-1.0.0.tar.gz
└── SPECS
    └── my.spec
```

## Example usage

A full example can be found in [this my_rpm example](https://github.com/robertdebock/my_rpm).

`.github/workflows/rpmbuild.yml`:

```yaml
---
name: Build RPM

on:
  - push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: checkout
        uses: actions/checkout@v2
      - name: rpmbuild
        uses: robertdebock/rpmbuild-action@1.1.1
```
