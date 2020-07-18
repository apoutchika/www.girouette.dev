---
date: 2020-07-05T11:05:20+02:00
draft: false
---

> Girouette it's a DNS proxy, load balancer (compatible with traefik label) and certificate generator for working with docker for development.

## Install or Update

### Requirements :

- Docker
- Ports : `80`, `443` and `53`
- Set you'r primary DNS server to `127.0.0.1`

With curl:

```sh
$ bash -c "$(curl -fsSL https://raw.githubusercontent.com/apoutchika/proxy/master/girouette.sh)"
```

With wget :

```sh
$ bash -c "$(wget https://raw.githubusercontent.com/apoutchika/proxy/master/girouette.sh -O -)"
```
