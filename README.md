# homelab-live

Software running on my homelab #gitops #argocd #applicationsets

- [x] jellyfin for serving media and editing playlists
- [ ] crowdsec for DOS protection
- [ ] linkerd for encryption in transit
- [x] traefik customizations (TLS etc)
- [x] expose admin services (argocd, kubernetes-dashboard, traefik, etc) via tailnet with magicDNS and Tailscale certificate for TLS
- [x] have a volume mount for USB drive for the media files for jellyfin
- [x] PVC for jellyfin to access the NFS PVs
- [ ] for multinode clusters, deploy Metalb loadbalancer w/ Helm
- [ ] To encrypt packets between kublets, switch the CNI from flannel to Cilium


### K8s-Dashboard login
The bearer token is saved in a kubernetes secret. To get the token: 
```bash
kubectl get secret admin-user -n kubernetes-dashboard -o jsonpath="{.data.token}" | base64 -d
```
Paste it into the UI when asked.
