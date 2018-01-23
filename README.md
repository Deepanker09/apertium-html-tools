Apertium Html-tools
====================

[![CircleCI](https://circleci.com/gh/goavki/apertium-html-tools.svg?style=svg)](https://circleci.com/gh/goavki/apertium-html-tools)

[Apertium Html-tools](http://wiki.apertium.org/wiki/Apertium-html-tools) is a web application
providing a fully localised interface for text/document/website translation, analysis, and generation
powered by [Apertium](http://apertium.org). Designed with a dead simple build process, minimal
dependencies and only static resources for quick and easy deployment with any web server, it is
relatively lightweight and user-friendly. Html-tools relies on an Apertium HTTP API such as
[Apertium-apy](http://wiki.apertium.org/wiki/Apertium-apy) or [ScaleMT](http://wiki.apertium.org/wiki/ScaleMT)
(to a lesser extent). Development takes place on [GitHub](https://github.com/goavki/apertium-html-tools);
however, a read-only copy of the repository is kept in our [SVN repository (/trunk/apertium-tools/apertium-html-tools)](https://svn.code.sf.net/p/apertium/svn/trunk/apertium-tools/apertium-html-tools/).

More information along with instructions for localization is available on the [Apertium Wiki](http://wiki.apertium.org/wiki/Apertium-html-tools).

Prerequisites
----------------

* Python 3
* curl

Setup
-------

1. Copy `config.conf.example` to `config.conf` and edit it.
1. Then type `make`.

Running
----------

The static files within `/build` (generated by `make`) can be served by any server.
You can use whatever you like, including Apache or even just Python's HTTP server.
For example, to run on locally on `http://localhost:8080` you can do the following:

    python3 -m http.server 8080

A completely local setup with language data and translation from Apertium, an APy
instance, and Nginx to serve Html-tools is provided through [Docker](https://www.docker.com/).
After installing Docker, simply run the following and check `http://localhost:4545`.
Any changes to the local version of Html-tools will trigger a `make`.

    docker-compose up

For production usage, remember to

1. Build with `jsmin`, `csscompressor` and `htmlmin` installed through `pip`.
1. Enable gzip compression on your server.

Contributing
------------

[CircleCI](https://circleci.com/) runs tests and generates build artifacts including
a live copy of Html-tools using `config.conf.example`.

