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

```
kubectl create ns flux
fluxctl install --generate-manifest=true --git-user=airwavetechio --git-email=tony@airwavetech.io --git-url=git@github.com:airwavetechio/hello-world --git-path=flux/releases/namespaces,flux/releases/airwave-stage --git-branch master --namespace=flux | kubectl apply -f -
```



## Knative
With Knative installed...
`kubectl apply -f knative-service.yml`



## Skaffold
`skaffold dev` OR
`skaffold run`

