[![CircleCI](https://circleci.com/gh/bitnami/bitnami-docker-codeigniter/tree/master.svg?style=shield)](https://circleci.com/gh/bitnami/bitnami-docker-codeigniter/tree/master)

# Bitnami CodeIgniter Development Container

## TL;DR;

### Local workspace

```bash
$ mkdir ~/myapp && cd ~/myapp
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-codeigniter/master/docker-compose.yml
$ docker-compose up
```

## Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* Bitnami images are built on CircleCI and automatically pushed to the Docker Hub.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading linux distribution.

## Introduction

[Codeigniter](https://www.codeigniter.com/) is a powerful PHP framework with a very small footprint, built for developers who need a simple and elegant toolkit to create full-featured web applications.

The Bitnami CodeIgniter Development Container has been carefully engineered to provide you and your team with a highly reproducible CodeIgniter development environment. We hope you find the Bitnami CodeIgniter Development Container useful in your quest for world domination. Happy hacking!

[Learn more about Bitnami Development Containers.](https://docs.bitnami.com/containers/how-to/use-bitnami-development-containers/)

# Supported tags and respective `Dockerfile` links

> NOTE: Debian 8 images have been deprecated in favor of Debian 9 images. Bitnami will not longer publish new Docker images based on Debian 8.

Learn more about the Bitnami tagging policy and the difference between rolling tags and immutable tags [in our documentation page](https://docs.bitnami.com/containers/how-to/understand-rolling-tags-containers/).


* [`3-ol-7`, `3.1.9-ol-7-r83` (3/ol-7/Dockerfile)](https://github.com/bitnami/bitnami-docker-codeigniter/blob/3.1.9-ol-7-r83/3/ol-7/Dockerfile)
* [`3-debian-9`, `3.1.9-debian-9-r75`, `3`, `3.1.9`, `3.1.9-r75`, `latest` (3/debian-9/Dockerfile)](https://github.com/bitnami/bitnami-docker-codeigniter/blob/3.1.9-debian-9-r75/3/debian-9/Dockerfile)

Subscribe to project updates by watching the [bitnami/codeigniter GitHub repo](https://github.com/bitnami/bitnami-docker-codeigniter).


## Getting started

The quickest way to get started with the Bitnami CodeIgniter Development Container is using [docker-compose](https://docs.docker.com/compose/).

Begin by creating a directory for your CodeIgniter application:

```bash
$ mkdir ~/myapp
$ cd ~/myapp
```

Download the [docker-compose.yml](https://raw.githubusercontent.com/bitnami/bitnami-docker-codeigniter/master/docker-compose.yml) file in the application directory:

```bash
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-codeigniter/master/docker-compose.yml
```

Finally launch the CodeIgniter application development environment using:

```bash
$ docker-compose up
```

The above command creates a container service for CodeIgniter development and bootstraps a new CodeIgniter application, named `myapp` in working directory. You can use your favorite IDE for developing the application.

After the builtin PHP application server has been launched, visit http://localhost:8000 in your favorite web browser and you'll be greeted the CodeIgniter welcome page.

## Executing commands

Commands can be launched inside the `myapp` CodeIgniter Development Container with `docker-compose` using the [exec](https://docs.docker.com/compose/reference/exec/) command.

> **Note**:
>
> The `exec` command was added to `docker-compose` in release [1.7.0](https://github.com/docker/compose/blob/master/CHANGELOG.md#170-2016-04-13). Please ensure that you're using `docker-compose` version `1.7.0` or higher.

The general structure of the `exec` command is:

```bash
$ docker-compose exec <service> <command>
```

where `<service>` is the name of the container service as described in the `docker-compose.yml` file and `<command>` is the command you want to launch inside the service.

Following are a few examples:

- Create a new project named `foo`:

  ```bash
  $ docker-compose run myapp nami execute codeigniter createProject foo
  ```

  Additionally, in the `docker-compose.yml` file you need to update the `CODEIGNITER_PROJECT_NAME` environment variable to `foo` so that the built-in PHP application server serves the application from the `foo` directory.

## Issues

If you encountered a problem running this container, you can file an [issue](../../issues/new). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version (`$ uname -a`)
- Docker version (`$ docker version`)
- Docker info (`$ docker info`)
- Docker image version (`$ echo $BITNAMI_IMAGE_VERSION` inside the container)
- Steps to reproduce the issue.

## License

Copyright (c) 2015-2016 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  <http://www.apache.org/licenses/LICENSE-2.0>

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
