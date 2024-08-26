# Redis

![Build, scan & push](https://github.com/Polarix-Containers/redis/actions/workflows/build.yml/badge.svg)

### Features & usage
- Built on the [Docker Community's Alpine-based image](https://github.com/redis/docker-library-redis), to be used as a drop-in replacement.
- Unprivileged image: you should check your volumes' permissions (eg `/data`), default UID:GID is 991:1000.
- Removes unnecessary gosu SUID binary.

### Licensing
- The code in this repository is licensed under the Apache License. 😇
- The image is built on `docker.io/redis`, which is under the BSD license. Copyright to the base image belongs to Docker Inc.
- Any image built by Polarix Containers is provided under the combination of license terms resulting from the use of individual packages.
