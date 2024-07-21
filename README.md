# k3s-gitops

Documentation of installation/setup/config for k3s cluster with flux and podinfo example deployment.

## Description

GitOps repository.

## Getting Started

### Dependencies

* Linux VM
* Github
* k3s
* flux
* DNS

### Installing

* Setup VM in Hetzner cloud - https://docs.hetzner.com/cloud/servers/getting-started/creating-a-server/
* Setup DNS A record - https://docs.hetzner.com/dns-console/dns/manage-records/managing-a-records/
```
sudo apt update && sudo curl -sfL https://get.k3s.io | sudo sh -s - server --cluster-init --token 9315de2a6bf976864
```
* Install/Setup FluxCD 
```
curl -s https://fluxcd.io/install.sh | sudo bash
```
* Setup Flux to read form Github
```
export GITHUB_TOKEN={github_token}
flux bootstrap github \   
--token-auth \
--owner=petraki-ops \
--repository=k3s-gitops \
--branch=main \
--path=k3s \
--personal
```

## Authors

Contributors names and contact info:

* Petraki Petrov - http://podinfo.ppetrov.info/