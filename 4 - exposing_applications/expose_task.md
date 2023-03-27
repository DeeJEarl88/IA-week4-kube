### 1 - What do you see and what is happening after exposing via ClusterIP?

```
Sometimes i see a `Welcome to nginx` page and sometimes i see the current date being logged.
This service is picking up the `pod-nginx` and the `labeled-pod` which serve two different index.html files.
The service is aggregating all pods with the nginx label and exposing them for use on port 80.
Port 80 is internal and available to kubernetes which is why we must proxy to access it.
```

### 2 - What is happening? How is the nodeport behaving different? Why?

```
With this service i'm always seeing the current date being logged.
This is because the selectors included dev and only aggregated the `labeled-pod`.
With this approach we have both an interal kubernetes IP as to aggregate our service and pods under.
But we also have a fixed IP on our nodes allowing us to access our kubernete IP instead of proxying
```