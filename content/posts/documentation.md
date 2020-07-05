---
date: 2020-07-05T11:05:00+02:00
draft: false
---

## Documentation

You must use :

- External network
- Label for list domain

### External Network

Create a girouette network or other name (Girouette auto discover it)

```sh
$ docker network create girouette
```

#### With docker-compose :

```yaml
version: '3.7'

services:
  whoami:
    image: emilevauge/whoami
    networks:
      - girouette # Use external network
    labels:
      girouette.domains: whoami.devel:80,test.local:80 # List domains and port (default is 80)

networks:
  girouette: # Use external network
    external:
      name: girouette
```

#### With docker

```sh
$ docker run \
  --network girouette \
  --label girouette.domains="whoami.devel:80" \
  emilevauge/whoami
```

### Compatible with traefik labels

```yaml
version: '3.7'

services:
  whoami:
    image: emilevauge/whoami
    networks:
      - girouette # Use external network
    labels:
      traefik.frontend.rule: 'Host:whoami.devel'
      traefik.port: 80

networks:
  girouette: # Use external network
    external:
      name: girouette
```
