## REQUIREMENTS

In order for the dashboard ingress to work, a kubernetes secret named 
`traefik-tailscale-config` must be created with stringData like the following:

```yaml
configValues: |-
  ingressRoute:
    dashboard:
     matchRule: Host(`traefik.my-tailnet-name.ts.net`)
```

The HelmChartConfig defined in ./helm-chart-config.yaml uses it in the 
`valuesSecrets` section.

ALSO, the tailscale kubernetes-operator requires that secret named `operator-oauth`
be set that contains the oauth credentials from tailscale.
