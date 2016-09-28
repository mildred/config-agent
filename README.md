config-agent
============

config-agent is a tool that let you administrate your server by connecting to it using ssh. Special commands can be installed in `/usr/lib/config/config-*`.

Installation
============

Use `fpmbuild` to generate a package for your distribution:

- `go get github.com/mildred/fpmbot/cmd/fpmbuild`
- `cd path/to/config-agent`
- `fpmbuild -t deb|rpm|...`

First Use
=========

You can access the config from the command line on the server or from ssh. The following are identical:

    server# config help
    laptop$ ssh config@server help

Before using ssh to configure your system, you have to add your public key. Just:

    server# config add-user ssh-ed25519 AAAAC3NzaC1lZDI1NTE5A........oUT7Qz yourname@laptop

Service integration
===================

To integrate your service in the config agent, just put a command in `/usr/lib/config`. The command will be made available.
