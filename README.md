# krateo-installer-charts

Helm charts for the Krateo installer, published as OCI artifacts to
`oci://ghcr.io/braghettos/krateo` by GitHub Actions on tag push (`v*`).

## Charts

| Chart | Version | Description |
|-------|---------|-------------|
| `frontend` | 1.0.10 | Krateo frontend |
| `krateo-autopilot` | 0.1.0 | Krateo Autopilot agents, MCP servers, models, prompts |
| `otel-collector-deployment` | 0.1.0 | Cluster-level OpenTelemetry collector (K8s events to ClickHouse) |
| `otel-collector-daemonset` | 0.1.0 | Node-level OpenTelemetry collector (logs/metrics to ClickHouse) |
| `krateo-sse-proxy` | 0.1.0 | SSE proxy streaming K8s events from ClickHouse to browsers |

## Release

Push a tag matching `v*` (e.g. `v1`). The `release-oci` workflow packages each
chart under `charts/<name>/` and `helm push`es it to the OCI registry.

## Consume

```sh
helm show chart oci://ghcr.io/braghettos/krateo/frontend --version 1.0.10
```
