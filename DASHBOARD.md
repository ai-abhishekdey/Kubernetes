# Kubernetes Dashboard

* Install [non-root user mode]
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
```
* check kubernetes-dashboard pod
```
kubectl get pods -n kubernetes-dashboard

```
* Create admin access
```
kubectl create serviceaccount dashboard-admin -n kubernetes-dashboard

```
```
kubectl create clusterrolebinding dashboard-admin \
  --clusterrole=cluster-admin \
  --serviceaccount=kubernetes-dashboard:dashboard-admin

```

* Get login token

```
kubectl -n kubernetes-dashboard create token dashboard-admin

```

* Start Dashboard

```
kubectl proxy

```

* Paste the below url and Login using the token.

```
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

```

