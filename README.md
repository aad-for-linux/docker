# Azure Active Directory for Linux Dockerfiles


[![MIT](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://spdx.org/licenses/MIT.html)
[![GitHub Actions](https://img.shields.io/github/workflow/status/aad-for-linux/docker/main?style=flat-square)](https://github.com/aad-for-linux/docker/actions/workflows/main.yml)

## Building

This repository utilizes `docker-compose` to build these images.

To build all images at once, run `docker-compose build`.

To build a specific image, specify a service name, e.g., `docker-compose build libnss-aad-ubuntu`.

**Note: this only builds a docker image; it does not compile any of the project code.**

## Running

To run a specific image, specify a service name, e.g., `docker-compose run pam-aad-ubuntu`.

Now you can begin developing the code for each project from within the docker container.

## License

SPDX-License-Identifier: [MIT](COPYING)
