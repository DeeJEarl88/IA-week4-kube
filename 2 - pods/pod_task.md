### 1 - Enter command for creation of pod_1.yml

```
kubectl apply -f ./'2 - pods'/manifests/pod_1.yml
```

### 2 - Enter command used to verify the pod_1.yml (describe or proxy with url)

```
kubectl proxy --port=8000
curl http://localhost:8000/api/v1/dev/pods/pod-nginx/proxy/
```

### 3 - Describe how the containers are working together after applying pod_2.yml

```
With the addition of a shared volume, container pod-content is writing 