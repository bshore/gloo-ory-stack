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
  --kubernetes-version=v1.23.0 \
  --cpus max \
  --memory max \
  --driver=docker \
  --disk-size='60g'
```

Run `tilt up` from the repo root and hit spacebar to open the UI

Note: The Tilt extension `helm_resource` has a dependency on `python3` as a _named_ binary/exe, which isn't really a thing on Windows. You may have Python 3+ installed (I have Python 3.10.x), to solve this I made a copy of my `python.exe` and named it `python3.exe` which seemed to work.

Referencing this example for some config setup:
https://github.com/ory/examples/tree/master/kratos-oathkeeper-kong

## TODOs:

- expose ports / virtual service / domain for kratos pod

#### Commands

- Connect to postgres
  - `kubectl -n kratos get pods` (copy the kratos-pg pod name)
  - `kubectl -n kratos exec -it {copied pod name} -- psql postgres://dev:password@localhost:5432/kratosdb`
