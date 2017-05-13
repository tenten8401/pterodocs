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
|Minecraft|:fa-check:|:fa-check:|:fa-check:|:fa-check:|
|Source Based|:fa-check:|:fa-times:|:fa-check:|:fa-check:|
|ARK|:fa-check:|:fa-times:|:fa-check:|:fa-times:|
|Voice Servers|:fa-check:|:fa-times:|:fa-check:|:fa-times:|
|Add Your Own Games & Services|:fa-check:|:fa-times:|:fa-check:|:fa-check:|
|Two-Factor Auth|:fa-check:|:fa-check:|:fa-times:|:fa-check:|
|File Manager|Custom|Net2FTP|Custom|:fa-times:|
|Sub-Users|:fa-check:|:fa-check:|:fa-check:|:fa-times:|
|External File Access|:fa-check:|:fa-check:<sup>[3](#anchor-3)</sup>|:fa-times:|:fa-check:|
|MySQL DB Creation|:fa-check:|:fa-times:|:fa-times:|:fa-times:|
|Docker Based|:fa-check:|:fa-minus: <sup>[4](#anchor-4)</sup>|:fa-times:|:fa-times:|
|Remote Nodes|:fa-check:|:fa-check:|:fa-check:|:fa-check:|
|Panel API|:fa-check:|:fa-check:|:fa-check:|:fa-times:|
|Minecraft Plugin System|:fa-check:|:fa-check:|:fa-check:|:fa-times: |
|Core Plugin System|:fa-times:|:fa-times:|:fa-check:|:fa-times:|
|Template System|:fa-check:|:fa-check:|:fa-check:|:fa-times:|
|Multi-Language|:fa-minus:<sup>[5](#anchor-5)</sup>|:fa-check:|:fa-check:|:fa-minus:|
|Backup System|:fa-times:|:fa-check:|:fa-check:|:fa-times:|
|Additional Port Management|:fa-check:|:fa-times:|:fa-check:|:fa-times:|
|Locked Ports|:fa-check:|:fa-times:|:fa-check:|:fa-minus:|
|Scheduled Tasks|:fa-check:|:fa-check:|:fa-check:|:fa-times:|
|Responsive Design|:fa-check:|:fa-times:<sup>[8](#anchor-8)</sup>|:fa-check:|:fa-check:|
|Push Notifications|:fa-times:|:fa-times:|:fa-check:|:fa-times:|
| | | | | |

<a id="anchor-1">1</a> — Refers to the panel being entirely self-contained and not needing any additional dependencies to be installed separately (MySQL, Webserver, etc.).

<a id="anchor-2">2</a> — Daemon is self-contained, front-end requires standard L<sup>A</sup>/<sub>E</sub>MP setup.

<a id="anchor-3">3</a> — Multicraft uses FTP. Pterodactyl and PufferPanel both make use of SFTP.

<a id="anchor-4">4</a> — Docker is optional in Multicraft where Pterodactyl requires it.

<a id="anchor-5">5</a> — Language support built-in, however still some languages missing and not every string is able to be translated currently.

<a id="anchor-6">6</a> — Refers to the ability to assign specific IPs and ports to a server that can be used and managed by users.

<a id="anchor-7">7</a> — Refers the the inability for users to open unassigned ports on their server through the use of plugins or other means. Multicraft overwrites server configurations to keep the port assigned but does not prevent opening additional ports through plugins.

<a id="anchor-8">8</a> — Multicraft uses a separate mobile theme rather than a responsive design.