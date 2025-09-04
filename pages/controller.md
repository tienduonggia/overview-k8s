## Replication Controller

- RC is a resource that will create and manage pods. Ensure the number of running pods equals the number defined in the YAML file.
- Recreates pods if they fail, get deleted, or node crashes.

<div grid grid-cols-2>
<v-click>
<img src="/img_1.png" />
</v-click>
<v-click>
<img src="/img_2.png" width="300px" height="100px" />
</v-click>
</div>

---
layout: two-cols
layoutClass: gap-16
transition: fade-out
---

<img src="/img_3.png" />

::right::

```yml
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx
spec:
  replicas: 3
  selector:
    app: nginx
  template:
    metadata:
      name: nginx
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx
          ports:
            - containerPort: 80

```

 

---

## Daemon Sets

This DaemonSets will deploy to each node a single pod, 
and will definitely have how many pods there are for how many nodes, it will not have replicas attribute


<div grid grid-cols-2>
<v-click>
<img src="/img_4.png" width="500px" />
</v-click>
<v-click>

```yml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: ssd-monitor
spec:
  selector:
    matchLabels:
      app: ssd-monitor
  template:
    metadata:
      labels:
        app: ssd-monitor
    spec:
      nodeSelector:
        disk: ssd
      containers:
        - name: main
          image: luksa/ssd-monitor
```

</v-click>
</div>


 

