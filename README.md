# CRUX Docker Base Image

[CRUX](https://crux.nu/) linux image for [Docker](https://www.docker.com)

This is a docker image containing only the 'core' ports from CRUX and no configuration. It is intended to be as generic as possible so you can use it however you like.

Basic usage:
```
docker import crux-3.5-docker-base-image.tar.xz crux:3.5
```

One example usage would be to create a container to test building of a port and all its dependencies:
```
docker run -it --name crux-3.5-builder crux:3.5
<make required changes such as adding a build user, installing fakeroot, enabling ports collections, etc., then exit the container>
docker commit crux-3.5-builder crux:3.5-builder
```

Thereafter the 'crux-3.5-builder' image would be available for quick port build testing.
