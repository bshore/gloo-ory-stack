# gloo resources
k8s_yaml(kustomize('./k8s/gloo_overlay'))

k8s_resource(workload='api-server', labels=["gloo"])
k8s_resource(workload='discovery', labels=["gloo"])
k8s_resource(workload='extauth', labels=["gloo"])
k8s_resource(workload='gateway', labels=["gloo"])
k8s_resource(workload='gateway-proxy', port_forwards=["0.0.0.0:443:8443", "0.0.0.0:80:8080"], labels=["gloo"])
k8s_resource(workload='gloo', labels=["gloo"])
k8s_resource(workload='observability', labels=["gloo"])
k8s_resource(workload='rate-limit', labels=["gloo"])
k8s_resource(workload='redis', labels=["gloo"])
k8s_resource(workload='gateway-certgen', labels=["gloo"])

# kratos resources
k8s_yaml(kustomize('./k8s/kratos'))
# https://github.com/tilt-dev/tilt-extensions/tree/master/helm_resource
load('ext://helm_resource', 'helm_resource')
helm_resource(
  name='kratos',
  chart='ory/kratos',
  namespace='kratos',
  resource_deps=['kratos-pg'],
  flags=['-f', './k8s/kratos/values.yaml'],
)
k8s_resource(workload='kratos-pg', labels=['kratos'])
k8s_resource(workload='kratos', labels=['kratos'])
