# hello-world
 A hello world app for demos

## Summary
This hello world application is a node app that has been "dockerized". The purpose of this app is to:
* An application used for Kubernetes deployments and testing
* Istio ingress using minkube

## Build locally
```docker build -t airwavetechio\hello-world:<tag>```




## For GitOps
### Install Flux into your cluster

### Linux / Mac
```
kubectl create ns flux
export GHUSER=githubusername 
fluxctl install --git-user=${GHUSER} --git-email=${GHUSER}@users.noreply.github.com --git-url=git@github.com:${GHUSER}/hello-world --git-path=flux --namespace=flux | kubectl apply -f -
fluxctl identity --k8s-fwd-ns flux
Then copy the deploy key to your repo
fluxctl --k8s-fwd-ns flux sync
```


### Windows 
kubectl create ns flux
set GHUSER=githubusername 
fluxctl install --git-user=%GHUSER% --git-email=%GHUSER%@users.noreply.github.com --git-url=git@github.com:%GHUSER%/hello-world --git-path=flux --namespace=flux | kubectl apply -f -
fluxctl identity --k8s-fwd-ns flux
Then copy the deploy key to your repo
fluxctl --k8s-fwd-ns flux sync