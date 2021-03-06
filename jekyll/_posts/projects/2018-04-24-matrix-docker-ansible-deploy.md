---
layout: project
title: matrix-docker-ansible-deploy
categories: projects other
description: Matrix server setup using Ansible and Docker
author: spantaleev
maturity: Beta
language: Shell
license: 
repo: https://github.com/spantaleev/matrix-docker-ansible-deploy
---

# {{ page.title }}
This Ansible playbook is meant to easily let you run your own [Matrix](http://matrix.org/) homeserver.

That is, it lets you join the Matrix network with your own `@<username>:<your-domain>` identifier, all hosted on your own server.

Using this playbook, you can get the following services configured on your server:

- a [Matrix Synapse](https://github.com/matrix-org/synapse) homeserver - storing your data and managing your presence in the [Matrix](http://matrix.org/) network

- (optional) [Amazon S3](https://aws.amazon.com/s3/) storage for your Matrix Synapse's content repository (`media_store`) files using [Goofys](https://github.com/kahing/goofys)

- (optional default) [PostgreSQL](https://www.postgresql.org/) database for Matrix Synapse - providing better performance than the default [SQLite](https://sqlite.org/) database. Using an external PostgreSQL server [is possible](#using-an-external-postgresql-server-optional) as well

- a [STUN/TURN server](https://github.com/coturn/coturn) for WebRTC audio/video calls

- (optional default) a [Riot](https://riot.im/) web UI, which is configured to connect to your own Matrix Synapse server by default

- free [Let's Encrypt](https://letsencrypt.org/) SSL certificate, which secures the connection to the Synapse server and the Riot web UI

- (optional default) an [nginx](http://nginx.org/) web server, listening on ports 80 and 443 - standing in front of all the other services. Using your own webserver [is possible](#using-your-own-webserver-instead-of-this-playbooks-nginx-proxy-optional)

Basically, this playbook aims to get you up-and-running with all the basic necessities around Matrix, without you having to do anything else.

Repository: <{{page.repo}}>
