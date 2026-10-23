# hello-config

GitOps configuration repo for the lab: what runs in the cluster is what is described here.

```
charts/hello-service/          Helm chart of the service (Deployment, Service, ServiceMonitor)
environments/lab/values.yaml   Lab overrides; image.tag is bumped by the hello-service pipeline
```

Coming next:

- `argocd/` — Argo CD Applications (app of apps), so a fresh cluster rebuilds itself from this repo
- `platform/monitoring/` — kube-prometheus-stack values, dashboards, alert rules and SLOs

## Render the chart locally

```bash
helm template hello-service charts/hello-service -f environments/lab/values.yaml
```
