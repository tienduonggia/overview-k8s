## Pod

Pod is the smallest unit in Kubernetes, used to deploy and run applications managed by Kubernetes. Run on Node

A pod wraps one or more containers that run together on a single worker node, with each container sharing resources.

Each pod will have own IP

<v-click>
<img src="/img.png" />
</v-click>

 

---

## Example

```yml
apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
spec:
  containers:
    - name: myapp-container
      image: nginx:1.25
      ports:
        - containerPort: 80
      # Resource requests & limits
      resources:
        requests:
          memory: "128Mi"
          cpu: "250m"
        limits:
          memory: "256Mi"
          cpu: "500m"

```
--- 

 Example

```yml
      # Liveness probe (check if container is healthy)
      livenessProbe:
        httpGet:
          path: /
          port: 80
        initialDelaySeconds: 10 #start after 10s when init container
        periodSeconds: 5 # repeat 5s
      # Readiness probe (check if container is ready to serve traffic)
      readinessProbe:
        httpGet:
          path: /
          port: 80
        initialDelaySeconds: 5
        periodSeconds: 5

```

 