# XRd Tools

This repository contains tools for working with XRd containers.

See [the docs]() *[TODO: Add link to docs]* for more details and guidance.

See [CHANGELOG.md](CHANGELOG.md) for a record of changes that have been made.

See [docs/version-compatibility.md](docs/version-compatibility.md) for the compatibility statement across versions.


## Download

Download an archive from the [releases page]() *[TODO: link release page]*.


## System Dependencies

XRd is only able to run on Linux, therefore the scripts provided here are also targeting Linux.

The scripts are implemented in bash and python3, which must therefore be found on `PATH`.
All active versions of python3 are supported.

The `xr-compose` script also requires `docker-compose` (v1) to be on `PATH` and for the `PyYAML` python package be installed (e.g. in an active virtual environment).


## Repo Contents

See [the docs]() *[TODO: Add link to docs]* for a full explanation of how to use the tools.

### `scripts/`

* `host-check` - Check the host is set up correctly for running XRd containers.
* `launch-xrd` - Launch a single XRd container, or use `--dry-run` to see the args required.
* `xr-compose` - Launch a topology of XRd containers (wraps `docker-compose`).
* `apply-bugfixes` - Create a new XRd image with bugfixes installed on top of a base image.

### `samples/`

Sample files, e.g. `xr-compose` topology samples.

### `templates/`

Template files, whether illustrative scripts or template config/topology files.

### `tests/`

Tests for the scripts.


## Versioning Scheme

This project loosely follows semantic versioning.
Version numbers consist of major, minor and patch, e.g. `v1.0.2`.

Cosmetic changes will involve a patch bump, moderate (possibly breaking) changes will be a minor bump, while significant backwards-incompatible changes require a major version bump.

Major version bumps are avoided as much as possible since we want to maintain backwards compatibility!
An example of a breaking change requiring a major version bump would be dropping support for an old XR release version, however this should not be a common occurrence (we aim to maintain compatibility of at least 3 release versions at a time).

Minor version bumps may introduce incompatibilities with previous invocations as long as these are documented in [version-compatibility.md](docs/version-compatibility.md), and as long as there's still a way to tweak the invocation to work with the same range of XR releases.


## Contributing

Thanks for considering contributing to the project!

Check out the repo's [open issues]() *[TODO: Add link when repo is finalised]* or see [CONTRIBUTING.md](CONTRIBUTING.md) for more contributing guidelines.