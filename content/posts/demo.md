---
date: 2020-07-05T11:05:10+02:00
draft: false
---

## What is Girouette ?

### DNS Server

When you'r install Girouette, choice the domain extentions to redirect in localhost :

![Dns proxy](/dns.jpg)

Configure you'r network connexion with primary DNS server `127.0.0.1`

### HTTPS

Girouette create SSL certificates autosigned for you. Just add an authority certificate to your browser after installation, the rest is done by itself.

![Https with Girouette](/https.jpg)

### Interface

You can go to https://girouette.devel/ and see real time interface :

- List of container started with domain label
- Click link to open, add to favorite or switch to http / https
- Stop docker-compose project

![interface](/interface.jpg)
