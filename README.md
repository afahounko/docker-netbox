# Netbox

NetBox is an IP address management (IPAM) and data center infrastructure management (DCIM) tool. Initially conceived by the network engineering team at [DigitalOcean](https://www.digitalocean.com/), NetBox was developed specifically to address the needs of network and infrastructure engineers.

NetBox runs as a web application atop the [Django](https://www.djangoproject.com/) Python framework with a [PostgreSQL](http://www.postgresql.org/) database. For a complete list of requirements, see `requirements.txt`. The code is available [on GitHub](https://github.com/digitalocean/netbox).

The complete documentation for NetBox can be found at [Read the Docs](http://netbox.readthedocs.io/en/stable/).

Questions? Comments? Please subscribe to [the netbox-discuss mailing list](https://groups.google.com/forum/#!forum/netbox-discuss), or join us on IRC in **#netbox** on **irc.freenode.net**!

# Docker and docker-compose

Install the latest version of Docker engine and docker-compose.
The project relies only on *Docker* and *docker-compose* meeting this requirements:

* The *Docker version* must be at least `1.13.0`.
* The *docker-compose version* must be at least `1.10.0`.

To ensure this, compare the output of `docker --version` and `docker-compose --version` with the requirements above.

## Quickstart

To get Netbox up and running:

```
$ git clone -b master https://github.com/ninech/netbox-docker.git
$ cd netbox-docker
$ docker-compose pull
$ docker-compose up -d
```

The application will be available after a few minutes.
Use `docker-compose port nginx 8080` to find out where to connect to.

```
$ echo "http://$(docker-compose port nginx 8080)/"
http://0.0.0.0:32768/

# Open netbox in your default browser on macOS:
$ open "http://$(docker-compose port nginx 8080)/"

# Open netbox in your default browser on (most) linuxes:
$ xdg-open "http://$(docker-compose port nginx 8080)/" &>/dev/null &
```

Default credentials:

* Username: **admin**
* Password: **admin**
* API Token: **0123456789abcdef0123456789abcdef01234567**
