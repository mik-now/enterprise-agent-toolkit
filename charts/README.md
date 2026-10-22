

## Charts

```
charts/
├── redis-stack/          ← Redis Stack (auth + ClusterIP + NetworkPolicy hardened)
├── pgvector/             ← PostgreSQL + pgvector
├── kuberay/              ← KubeRay RayCluster
└── openshell/            ← values overlay for the upstream OpenShell chart
```

The Agent Sandbox templates and the OpenShell provider profile are rendered by their
roles (`roles/<role>/templates/`), not by Helm.

## Adding a chart

1. Copy the chart directory here.
2. Run `helm dependency build charts/<name>/` only if it declares subchart dependencies
   in `Chart.yaml` (the vendored charts here embed their subcharts directly, so this is
   usually not needed).
3. Commit the full chart including any `charts/` subdirectory.
