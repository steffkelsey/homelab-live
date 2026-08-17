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

In order for the Tailscale kubernetes-operator to work, a secret named `operator-oauth`
must exist that contains the oauth credentials from tailscale.

```yaml
stringData: 
  client_id: <TS_CLIENT_ID>
  client_secret: <TS_CLIENT_SECRET>
```

In order for the letsencrypt certificate resolver to work, a secret named `namedotcom-api`
must exist that contains the API credentials for name.com.

```yaml
stringData: 
  username: <NAME_DOT_COM_USERNAME>
  token: <NAME_DOT_COM_API_TOKEN>
```
