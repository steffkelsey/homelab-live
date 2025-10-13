# homelab-live

Software running on my homelab #gitops #argocd #applicationsets

1. jellyfin for serving media and editing playlists
2. crowdsec for DOS protection
3. linkerd for encryption in transit
4. traefik customizations (TLS etc)
5. expose admin services (argocd, kubernetes console, etc) via tailnet with magicDNS and Tailscale certificate for TLS


## A BIG PROBLEM TO SOLVE

- Most Applications are Helm charts from remote repositories with values files 
stored in this repo (multiple sources)  
- Some Applications are Kubernetes manifests. For example, patching Traefik config  

SOLUTIONS:
1. make the traefik config (and any that are just manifests) come from it's own 
Helm chart and then everything is the same  
2. always use a template patch and handle the logic in the patch for multiple
sources   

