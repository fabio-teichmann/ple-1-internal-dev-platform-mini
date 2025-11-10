# ple-1-internal-dev-platform-mini

## Phase 1 - Platform Foundations
- [x] local cluster (Minikube)
- [x] install ArgoCD for GitOps
    - app of apps concept
    - manage deployments declaratively through GitOps
- [x] install Prometheus/Grafana for metrics
- [ ] deploy a sample app (FastAPI) via GitOps

### Storage (Garage)
For testing purposes, I am using Garage as a storage layer - since MinIO decided to be mostly commercial only a little while ago.

Grage is run with Docker locally for now using:
```bash
docker run \
  -d \
  --name garaged \
  --restart always \
  -p 3900:3900 -p 3901:3901 -p 3902:3902 -p 3903:3903 \
  -v /etc/garage.toml:/etc/garage.toml \
  -v /var/lib/garage/meta:/var/lib/garage/meta \
  -v /var/lib/garage/data:/var/lib/garage/data \
  dxflrs/garage:v2.1.0
```