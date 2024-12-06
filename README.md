# Redis

![Build 7, scan & push](https://github.com/Polarix-Containers/redis/actions/workflows/build-7.yml/badge.svg)
![Build 6, scan & push](https://github.com/Polarix-Containers/redis/actions/workflows/build-6.yml/badge.svg)

### Features & usage
- Built on the [Docker Community's Alpine-based image](https://github.com/redis/docker-library-redis), to be used as a drop-in replacement.
- Unprivileged image: you should check your volumes' permissions (eg `/data`), default UID:GID is 3008:3008.
- Removes unnecessary gosu SUID binary.

### Sample Docker Compose config

```
  redis:
    container_name: redis
    image: ghcr.io/polarix-containers/redis:7
    restart: unless-stopped
    volumes:
      - ./redis:/data:Z
    user: "3008:3008"
    read_only: true
    security_opt:
      - "no-new-privileges=true"
    cap_drop:
      - ALL
```

### Licensing
- The image is built on `docker.io/redis`.
- Starting on March 20th, 2024, Redis follows a dual-licensing model with the choice of the [Redis Source Available License v2 - RSALv2]((https://redis.io/legal/rsalv2-agreement/))⁠ or the [Server Side Public License v1 - SSPLv1](https://redis.io/legal/server-side-public-license-sspl/)⁠. Older versions of Redis (<=7.2.4) are licensed under [3-Clause BSD](https://opensource.org/license/bsd-3-clause)⁠. Please also view the [Redis License Overview](https://redis.io/legal/licenses/)⁠ and the [Redis Trademark Policy](https://redis.io/legal/trademark-policy/)⁠.
- Any image built by Polarix Containers is provided under the combination of license terms resulting from the use of individual packages.