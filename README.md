# gloo-ory-stack

Experimenting with Gloo Edge Proxy and the Ory Stack (Kratos, Hydra, Oathkeeper, Keto)

## Tools

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Tilt](https://docs.tilt.dev/install.html)

## Setup

Start a minikube cluster with

```
minikube start \
  --kubernetes-version=v1.23.0 \
  --cpus max \
  --memory max \
  --driver=docker \
  --disk-size='60g'
```

Run `tilt up` from the repo root and hit spacebar to open the UI

#### Commands

- Connect to postgres
  - `kubectl -n postgres get pods` (copy the postgres pod name)
  - `kubectl -n postgres exec -it {copied pod name} -- psql postgres://dev:password@localhost:5432/kratosdb`
