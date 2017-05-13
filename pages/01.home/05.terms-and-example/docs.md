---
title: 'Terms and Example Setup'
---

**Panel** — This refers to Pterodactyl Panel itself, and is what allows you to add additional nodes and servers to the system.

**Node** — A node is a physical server that runs the daemon.

**Daemon** — Called *Wings*, a service written in Javascript managing Docker and providing secure access for controlling mechanisms via the panels API.

**Server** — In this case, a server refers to an instance running that is created by the panel. These servers are created on nodes, and you can have multiple servers per node.

**Container** — Each server will be running inside an isolated [container](https://en.wikipedia.org/wiki/Operating-system-level_virtualization) to enforce hardware limitations (such as CPU and RAM) and avoid any interference between servers on one node.