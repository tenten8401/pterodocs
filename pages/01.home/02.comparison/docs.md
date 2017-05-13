---
title: 'Software Comparison'
---

| |Pterodactyl|Multicraft|AMP|PufferPanel|
|-|-|-|-|-|
|Price|Free|Commercial|Commercial|Free|
|Platform|:fa-linux:|:fa-linux: :fa-windows:|:fa-linux: :fa-windows:|:fa-linux:|
|Self-Contained<sup>[1](#anchor-1)</sup>|:fa-times:|:fa-minus: <sup>[2](#anchor-2)</sup>|:fa-check:|:fa-times:|
|Regular Updates|:fa-check:|:fa-check:|:fa-check:|:fa-check:|
|Support|Discord, Forums, Email|Email, Ticket System|Email, Discord, Ticket System|IRC,Discord, Forums|
|Supported Games| | | | |
|Minecraft|:fa-check:|:fa-check:|:fa-check:|:fa-check:|
|Source Based|:fa-check:|:fa-times:|:fa-check:|:fa-check:|
|ARK|:fa-check:|:fa-times:|:fa-check:|:fa-times:|
|Voice Servers|:fa-check:|:fa-times:|:fa-check:|:fa-times:|
|Add Your Own Games & Services|:fa-check:|:fa-times:|:fa-check:|:fa-check:|
| | | | | |
|Two-Factor Auth|:fa-check:|:fa-check:|:fa-times:|:fa-check:|
|File Manager|Custom|Net2FTP|Custom|:fa-times:|
|Sub-Users|:fa-check:|:fa-check:|:fa-check:|:fa-times:|
|External File Access| | | | |
|MySQL DB Creation| | | | |
|Docker Based| | | | |
|Remote Nodes| | | | |
|Panel API| | | | |
|Minecraft Plugin System| | | | |
|Core Plugin System| | | | |
|Template System| | | | |
|Multi-Language| | | | |
|Backup System| | | | |
|Additional Port Management| | | | |
|Locked Ports| | | | |
|Scheduled Tasks| | | | |
|Responsive Design| | | | |
|Push Notifications| | | | |
| | | | | |

<a id="anchor-1">1</a> — Refers to the panel being entirely self-contained and not needing any additional dependencies to be installed separately (MySQL, Webserver, etc.).

<a id="anchor-2">2</a> — Daemon is self-contained, front-end requires standard L<sup>A</sup>/<sub>E</sub>MP setup.

<a id="anchor-3">3</a> — Multicraft uses FTP. Pterodactyl and PufferPanel both make use of SFTP.

<a id="anchor-4">4</a> — Docker is optional in Multicraft where Pterodactyl requires it.

<a id="anchor-5">5</a> — Language support built-in, however still some languages missing and not every string is able to be translated currently.

<a id="anchor-6">6</a> — Refers to the ability to assign specific IPs and ports to a server that can be used and managed by users.

<a id="anchor-7">7</a> — Refers the the inability for users to open unassigned ports on their server through the use of plugins or other means. Multicraft overwrites server configurations to keep the port assigned but does not prevent opening additional ports through plugins.

<a id="anchor-8">8</a> — Multicraft uses a separate mobile theme rather than a responsive design.