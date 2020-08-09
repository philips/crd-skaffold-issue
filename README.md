Issues where if you have manifests installing CRDs and also using those CRDs skaffold run and dev fail.

A subsequent run will fix it because the app is partially deployed. But dev is unusable on this repo.


```
$ skaffold dev
WARN[0000] starting gRPC server on port 50053. (50051 is already in use)
WARN[0000] starting gRPC HTTP server on port 50054. (50052 is already in use)
Listing files to watch...
Generating tags...
Checking cache...
Tags used in deployment:
Starting deploy...
 - clusterrole.rbac.authorization.k8s.io/prometheus created
 - clusterrolebinding.rbac.authorization.k8s.io/prometheus created
 - customresourcedefinition.apiextensions.k8s.io/alertmanagers.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/podmonitors.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/prometheuses.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/prometheusrules.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/servicemonitors.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/thanosrulers.monitoring.coreos.com created
 - clusterrolebinding.rbac.authorization.k8s.io/prometheus-operator created
 - clusterrole.rbac.authorization.k8s.io/prometheus-operator created
 - deployment.apps/prometheus-operator created
 - serviceaccount/prometheus-operator created
 - service/prometheus-operator created
 - serviceaccount/prometheus created
 - Error from server (NotFound): error when creating "STDIN": the server could not find the requested resource (post prometheuses.monitoring.coreos.com)
Cleaning up...
 - clusterrole.rbac.authorization.k8s.io "prometheus" deleted
 - clusterrolebinding.rbac.authorization.k8s.io "prometheus" deleted
 - customresourcedefinition.apiextensions.k8s.io "alertmanagers.monitoring.coreos.com" deleted
 - customresourcedefinition.apiextensions.k8s.io "podmonitors.monitoring.coreos.com" deleted
 - customresourcedefinition.apiextensions.k8s.io "prometheuses.monitoring.coreos.com" deleted
 - customresourcedefinition.apiextensions.k8s.io "prometheusrules.monitoring.coreos.com" deleted
 - customresourcedefinition.apiextensions.k8s.io "servicemonitors.monitoring.coreos.com" deleted
 - customresourcedefinition.apiextensions.k8s.io "thanosrulers.monitoring.coreos.com" deleted
 - clusterrolebinding.rbac.authorization.k8s.io "prometheus-operator" deleted
 - clusterrole.rbac.authorization.k8s.io "prometheus-operator" deleted
 - deployment.apps "prometheus-operator" deleted
 - serviceaccount "prometheus-operator" deleted
 - service "prometheus-operator" deleted
 - serviceaccount "prometheus" deleted
exiting dev mode because first deploy failed: kubectl apply: exit status 1
$
```

```
$ skaffold run
Generating tags...
Checking cache...
Tags used in deployment:
Starting deploy...
 - clusterrole.rbac.authorization.k8s.io/prometheus created
 - clusterrolebinding.rbac.authorization.k8s.io/prometheus created
 - customresourcedefinition.apiextensions.k8s.io/alertmanagers.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/podmonitors.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/prometheuses.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/prometheusrules.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/servicemonitors.monitoring.coreos.com created
 - customresourcedefinition.apiextensions.k8s.io/thanosrulers.monitoring.coreos.com created
 - clusterrolebinding.rbac.authorization.k8s.io/prometheus-operator created
 - clusterrole.rbac.authorization.k8s.io/prometheus-operator created
 - deployment.apps/prometheus-operator created
 - serviceaccount/prometheus-operator created
 - service/prometheus-operator created
 - serviceaccount/prometheus created
 - Error from server (NotFound): error when creating "STDIN": the server could not find the requested resource (post prometheuses.monitoring.coreos.com)
kubectl apply: exit status 1
```
