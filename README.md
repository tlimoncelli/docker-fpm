# FPM (effing package manager) Docker Images

**tlimoncelli/fpm-{$distro}** are a series of Docker images to quickly get packages building in fpm on different Linux distributions.

This is a fork of **cdrx/fpm-{$distro}**, the only change being `/src`
is now `/tmp/src` so that it works with macOS's read-only root file
system.

Each distro has fpm installed and all the required dependencies to build packages for that platform. All images are 64bit.

You should mount the files you want to put into your package into `/tmp/src/`.

If you need to do any complicated setup in the environment before running `fpm` then it would be best to write a bash script, mount it into `/tmp/src/` and override the containers entrypoint when you run it. `fpm` is available to run in the system path.

## Images

* Ubuntu w/ fpm
  * `tlimoncelli/fpm-ubuntu:18.04` - bionic
  * `tlimoncelli/fpm-ubuntu:16.04` - xenial
  * `tlimoncelli/fpm-ubuntu:14.04` - trusty

* Debian w/ fpm
  * `tlimoncelli/fpm-debian:8`
  * `tlimoncelli/fpm-debian:7`

* Fedora w/ fpm
  * `tlimoncelli/fpm-fedora:24`
  * `tlimoncelli/fpm-fedora:23`
  * `tlimoncelli/fpm-fedora:22`
  * `tlimoncelli/fpm-fedora:21`
  * `tlimoncelli/fpm-fedora:20`

* CentOS w/ fpm
  * `tlimoncelli/fpm-centos:7`
  * `tlimoncelli/fpm-centos:6`
  * `tlimoncelli/fpm-centos:5`

The `:latest` tag will always point to the most recent release of the distro.

## Usage

```
docker run -v "$(pwd):/tmp/src/" tlimoncelli/fpm-ubuntu:16.04 fpm -s dir -t deb ..
```

```
docker run -v "$(pwd):/tmp/src/" tlimoncelli/fpm-fedora:24 fpm -s dir -t rpm ..
```
