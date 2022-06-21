# gloo-ory-stack

Experimenting with Gloo Edge Proxy and the Ory Stack (Kratos, Hydra, Oathkeeper, Keto)

## Tools

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [Helm](https://helm.sh/docs/intro/install/)
- [Tilt](https://docs.tilt.dev/install.html)

## Setup

Start a minikube cluster with

```
minikube start \
  --kubernetes-version=v1.19.14 \
  --cpus max \
  --memory max \
  --driver=docker \
  --disk-size='60g'
```

Run `tilt up` from the repo root and hit spacebar to open the UI

https://github.com/ory/examples/tree/master/kratos-oathkeeper-kong
