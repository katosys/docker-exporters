# exporters

[![Build Status](https://travis-ci.org/katosys/exporters.svg?branch=master)](https://travis-ci.org/katosys/exporters)

Prometheus exporters bundle.

#### node_exporter
```
docker run -it --rm --net host \
quay.io/kato/exporters:master node_exporter \
  -web.listen-address :9101
```

#### haproxy_exporter
```
docker run -it --rm --net host \
quay.io/kato/exporters:master haproxy_exporter \
  -haproxy.scrape-uri "http://localhost:9090/haproxy?stats;csv" \
  -web.listen-address :9102
```

#### zookeeper_exporter
```
docker run -it --rm --net host \
quay.io/kato/exporters:master zookeeper_exporter \
  -web.listen-address :9103 \
  quorum-1:2181 quorum-2:2181 quorum-3:2181
```

#### mesos_exporter
```
docker run -it --rm --net host \
quay.io/kato/exporters:master mesos_exporter \
  -slave http://$(hostname):5051 \
  -addr :9104
```
