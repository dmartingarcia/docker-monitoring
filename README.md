# docker-monitoring

It is part of a [set of repositories](https://github.com/search?q=user%3Admartingarcia+docker) that contain dockerised environments for small applications.

In this case, it contains a self-efficient *monitoring* setup, featuring Grafana, Prometheus, NodeExporter, Cadvisor, AlertManager and PushGateway.

## How to use it

```
cp .env.example .env
docker-compose up -d
```

And browse into `http://localhost:9002 to check Grafana Dashboard.

You should take a look into `.env` variable definitions before starting.

## Traefik integration`

It also contains a Traefik integration, that interact with this reverse proxy, routing request to each container in case it matches the specified domain

There's multiple subdomains exposed:
  - prometheus.your.domain.com
  - grafana.your.domain.com
  - nodeexporter.your.domain.com
  - pushgateway.your.domain.com
  - cadvisor.your.domain.com
  - alertmanager.your.domain.com

## .env setup

It contains a basic set of variables like:

- Credentials
- HTTP host that uses Traefik to match requests

Please take a look on that and :warning: create your own credentials :warning: in case you want to expose it to the public.

## Docker Traefik

If you want to use this Traefik integration, [take a look at this repository](https://github.com/dmartingarcia/docker-traefik)
