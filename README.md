# Redis

![Build 7, scan & push](https://github.com/Polarix-Containers/redis/actions/workflows/build-7.yml/badge.svg)
![Build 6, scan & push](https://github.com/Polarix-Containers/redis/actions/workflows/build-6.yml/badge.svg)

### Features & usage
- Built on the [Docker Community's Alpine-based image](https://github.com/redis/docker-library-redis), to be used as a drop-in replacement.
- Unprivileged image: you should check your volumes' permissions (eg `/data`), default UID:GID is 991:1000.
- Removes unnecessary gosu SUID binary.

### Sample Docker Compose config

```
  redis:
    container_name: redis
    image: ghcr.io/polarix-containers/redis:7
    restart: unless-stopped
    volumes:
      - ./redis:/data:Z
    user: "991:1000"
    read_only: true
    security_opt:
      - "no-new-privileges=true"
    cap_drop:
      - ALL
```

### Licensing
- The code in this repository is licensed under the Apache license. 😇
- The image is built on `docker.io/redis`, which is under the BSD license. Copyright to the base image belongs to Docker Inc.
- Any image built by Polarix Containers is provided under the combination of license terms resulting from the use of individual packages.
