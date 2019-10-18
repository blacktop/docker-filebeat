# docker-filebeat

[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org) [![Docker Stars](https://img.shields.io/docker/stars/blacktop/filebeat.svg)](https://hub.docker.com/r/blacktop/filebeat/) [![Docker Pulls](https://img.shields.io/docker/pulls/blacktop/filebeat.svg)](https://hub.docker.com/r/blacktop/filebeat/) [![Docker Image](https://img.shields.io/badge/docker%20image-84MB-blue.svg)](https://hub.docker.com/r/blacktop/filebeat/)

> Alpine Linux based [Filebeat](https://github.com/elastic/beats/tree/master/filebeat) Docker Image

---

## Why 🤔

This is initially focused on supporting the [Zeek](https://github.com/elastic/beats/tree/master/x-pack/filebeat/module/zeek) filebeats module.

I will add others if there is any demand or need later.

## Dependencies

- [alpine:3.10](https://hub.docker.com/_/alpine/)

## Image Tags

```bash
$ docker images

REPOSITORY               TAG          SIZE
blacktop/filebeat        latest       98MB
blacktop/filebeat        7.3,1        98MB
blacktop/filebeat        7.0.0        48.3MB
```

## Getting Started

Download or create `your.pcap` in current directory

```bash
$ docker run --init -d --name elasticsearch -p 9200:9200 blacktop/elasticsearch
$ docker run --init -d --name kibana --link elasticsearch -p 5601:5601 blacktop/kibana
$ docker run --init --rm -it -v `pwd`:/pcap \
                             --link kibana \
                             --link elasticsearch \
                             blacktop/filebeat -e
$ docker run --init --rm -it -v `pwd`:/pcap blacktop/filebeat:elastic -r your.pcap local
```

## Issues

Find a bug? Want more features? Find something missing in the documentation? Let me know! Please don't hesitate to [file an issue](https://github.com/blacktop/docker-filebeat/issues/new) and I'll get right on it.

## CHANGELOG

See [`CHANGELOG.md`](https://github.com/blacktop/docker-filebeat/blob/master/CHANGELOG.md)

## Contributing

[See all contributors on GitHub](https://github.com/blacktop/docker-filebeat/graphs/contributors).

Please update the [CHANGELOG.md](https://github.com/blacktop/docker-filebeat/blob/master/CHANGELOG.md) and submit a [Pull Request on GitHub](https://help.github.com/articles/using-pull-requests/).

## License

MIT Copyright (c) 2019 **blacktop**
