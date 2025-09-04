# Service

<v-click>

- A Service is a stable networking endpoint that groups together a set of Pods.

- The Service automatically forwards your request to one of the healthy Pods behind it.

- Even if Pods die and new ones are created, the Service IP and DNS name remain the same.
</v-click>

--- 

## ClusterIP

- Create 1 IP and 1 DNS(Service’s name) in cluster -> all pod in cluster can communicate together
- This IP is not accessible from outside the cluster (like from your laptop or the internet).

<div grid grid-cols-2>
<img src="/img_5.png" />

```yml

apiVersion: v1
kind: Service
metadata:
    name: my-clusterIP-service
spec:
    selector:
        app: nginx-appp
    type: ClusterIP
    ports:
    - name: http
      port: 80 #The port the Service exposes inside the cluster
      targetPort: 80   #The port inside the Pod’s container
      protocol: TCP

```

</div>

---

## NodePort

- Exposes Pods to the outside world using a port on each Node.
- Allocates a port in the range 30000–32767.
- Requests to NodeIP:NodePort get forwarded to the Pods.

<div grid grid-cols-2>
<img src="/7feabfe3-d734-42ad-ab1f-40d34959bda5.png">

```yml

apiVersion: v1
kind: Service
metadata:
    name: my-nodeport-service
spec:
    selector:
        app: nginx-appp
    type: NodePort
    ports:
    - name: http
      port: 80
      targetPort: 80
      nodePort: 30036
      protocol: TCP

```

</div>

 

---