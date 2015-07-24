Gitlab + ELK
============

This is a demo project showing how to integrate
[Gitlab](https://about.gitlab.com/) with the well-known **E**lasticsearch
**L**ogstash **K**ibana (ELK) stack. It features
[willdurand/docker-elk](https://github.com/willdurand/docker-elk) and
[willdurand/docker-logstash-forwarder](https://github.com/willdurand/docker-logstash-forwarder).

Quick Start
-----------

First, use the
[lc-tlscert](https://github.com/driskell/log-courier/blob/develop/src/lc-tlscert/lc-tlscert.go)
tool to generate self-signed SSL certificates:

```
$ wget https://raw.githubusercontent.com/driskell/log-courier/develop/src/lc-tlscert/lc-tlscert.go
$ go run lc-tlscert.go
```

Then, move the generated `selfsigned.{crt,key}` files to `etc/ssl/`:

```
$ mv selfsigned.{crt,key} etc/ssl/
```

Finally, up all the things!

```
$ docker-compose up
```


Configuration
-------------

The Kibana dashboard is available at: `http://<host>:10090/` (with `host`, an
address that points to your Docker environment e.g., `localhost` or
`192.168.59.103`).

Gitlab web interface is available at: `http://<host>:10080/` and its SSH port is
`10022`. A default account is configured: `root`/`5iveL!fe`. More information
at: [sameersbn/docker-gitlab](https://github.com/sameersbn/docker-gitlab).

A Docker `data` container is used to persist (and share) data among all other
containers.


Credits
-------

The Logstash configuration is based on [this
gist](https://gist.github.com/jerrac/d19e49e77819ef82de6e).


License
-------

This project is released under the MIT License. See the bundled LICENSE file for
details.
