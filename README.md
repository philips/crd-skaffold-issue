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
