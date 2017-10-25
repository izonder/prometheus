# Prometheus
Rancher stack for Prometheus monitoring

## How to

1. Run `rancher/server` with Prometheus metrics:

```
docker run -d \
    --volumes-from rancher-data \
    --restart=unless-stopped \
    -e CATTLE_PROMETHEUS_EXPORTER=true \
    -p 8080:8080 \
    -p 9108:9108 \
    rancher/server:latest
```

2. Change the IP for `rancher/server` at `docker-compose.yml`:

```
...
    extra_hosts:
    - rancher-server:<YOUR_IP> #change this to rancher/server exposed IP
...
```

3. Assign for maintenance host label `role=maintenance`
