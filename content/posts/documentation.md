---
date: 2020-07-05T11:05:00+02:00
draft: false
---

## Documentation

You must use Label for list domain

#### With docker-compose :

```yaml
version: "3.7"

services:
  whoami:
    image: emilevauge/whoami
    labels:
      girouette.domains: whoami.devel:80,test.local:80 # List domains and port (default is 80)
```

#### With docker

```sh
$ docker run \
  --label girouette.domains="whoami.devel:80" \
  emilevauge/whoami
```

### Compatible with traefik labels

```yaml
version: "3.7"

services:
  whoami:
    image: emilevauge/whoami
    labels:
      - "traefik.http.routers.whoami.rule=Host(`whoami.devel`)"
      - "traefik.http.services.whoami.loadbalancer.server.port=80"
```

### Compatible with old traefik labels

```yaml
version: "3.7"

services:
  whoami:
    image: emilevauge/whoami
    labels:
      traefik.frontend.rule: "Host:whoami.devel"
      traefik.port: 80
```
