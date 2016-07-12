# docker-exporters

[![Build Status](https://travis-ci.org/katosys/docker-exporters.svg?branch=master)](https://travis-ci.org/katosys/docker-exporters)

Prometheus exporters bundle

#### node_exporter
```
docker run -it --rm --net host \
katosys/exporters node_exporter \
  -web.listen-address :9101
```

#### haproxy_exporter
```
docker run -it --rm --net host \
katosys/exporters haproxy_exporter \
  -haproxy.scrape-uri "http://localhost:9090/haproxy?stats;csv" \
  -web.listen-address :9102
```

#### zookeeper_exporter
```
docker run -it --rm --net host \
katosys/exporters zookeeper_exporter \
  -web.listen-address :9103 \
  master-1:2181 master-2:2181 master-3:2181
```

#### mesos_exporter
```
docker run -it --rm --net host \
katosys/exporters mesos_exporter \
  -slave http://$(hostname):5051 \
  -addr :9104
```
