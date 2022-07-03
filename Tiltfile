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
k8s_resource(workload='kratos', labels=['kratos'], resource_deps=['postgres'])

# postgres resources
k8s_yaml(kustomize('./k8s/postgres'))
k8s_resource(workload='postgres', labels=['postgres'])

# selfservice-ui resources
k8s_yaml(kustomize('./k8s/selfservice-ui'))
k8s_resource(workload='selfservice', labels=['sso'])
