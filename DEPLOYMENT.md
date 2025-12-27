# Deployment

* Create deployment yaml file and apply

```
kubectl apply -f hp-app-deployment.yaml

```
* To see the pods
```
kubectl get pods
```
* Expose streamlit (port 8501)
```
kubectl expose deployment hp-app \
  --name=hp-app-streamlit \
  --type=ClusterIP \
  --port=8501 \
  --target-port=8501

```
* Expose fastapi (port 8000)

```
kubectl expose deployment hp-app \
  --name=hp-app-fastapi \
  --type=ClusterIP \
  --port=8000 \
  --target-port=8000
```

* Now access the app

```
kubectl port-forward service/hp-app-streamlit 8501:8501

```

* Check log live

```
kubectl logs -f deployment/hp-app
```

* To scale replicas

```
kubectl scale deployment hp-app --replicas=3
```
