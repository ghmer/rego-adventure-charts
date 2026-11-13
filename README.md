# Rego Adventure Helm chart

Helm chart for [Rego Adventure](https://github.com/ghmer/rego-adventure). Chart version equals the
application release: chart `2.6.0` deploys image `v2.6.0`.

```bash
helm repo add rego-adventure https://ghmer.github.io/rego-adventure-charts
helm repo update
helm install rego-adventure rego-adventure/rego-adventure \
  --namespace rego-adventure --create-namespace \
  --set config.domain=https://rego.example.com
```

Or from the OCI registry (Helm >= 3.8):

```bash
helm install rego-adventure oci://ghcr.io/ghmer/charts/rego-adventure \
  --namespace rego-adventure --create-namespace \
  --set config.domain=https://rego.example.com
```

`config.domain` must be the origin the browser uses; the application accepts it as the only CORS
origin. Release: bump `version` and `appVersion` in `charts/rego-adventure/Chart.yaml`, merge to
`main`, and the `Release Helm chart` workflow publishes a GitHub Release with the `.tgz`, updates
`index.yaml` on the `gh-pages` branch and pushes the chart to `ghcr.io/ghmer/charts/rego-adventure`.

Licensed under Apache-2.0, see [LICENSE](LICENSE).
