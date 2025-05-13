<img src="https://raw.githubusercontent.com/saveside/k8s/refs/heads/main/assets/honey-k8s.png" height="200">

# Save's Kubernetes setup

### 🐝 Cluster Nodes

| Role      | Hostname        | Location     | OS       | CPU  | RAM   | Machine |
|-----------|------------------|----------------|--------------------------|------|-------|-------------------|
| Master    | honeypie        | Hetzner Cloud   | Fedora Cloud     | Intel Xeon (Skylake, IBRS, no TSX) (2) @ 2.10 GHz (x86_64)| 4 GB | CX22  |
| Worker    | honeybee        | Hetzner Cloud   | Fedora Cloud     | Intel Xeon (Skylake, IBRS, no TSX) (4) @ 2.10 GHz (x86_64) | 8 GB | CX32 |


### 🍯 Components

- Anki Sync - For self-hosted Anki Flashcards
- ArgoCD - For GitOps, manages all the deployments (except itself and the CNI)
- Bin - A minimal pastebin
- cert-manager - For managing certificates
- Gatus - For health checks
- Kubernetes Reflector - For syncing secrets across namespaces
- Longhorn - For storage provisioning
- MetalLB - Load balancer, network policies
- Nextcloud - For file sharing
- Tailscale Operator - For VPN
- Traefik - Ingress controller
- Umami - For analytics
- Vaultwarden - For password management

### Installation

This setup uses Kustomize to manage the manifests. To install the setup, clone the repo and run the following commands:

```bash
kubectl kustomize --enable-helm | kubectl apply -f -
```

## Big Thanks

- Kreato's K8S Repository: <https://github.com/kreatoo/k8s/>
- mt190502's K8S Repository: <https://github.com/mt190502/k8s/>
