# Volume

- A Volume is a storage data
- Volumes persist data beyond the container lifecycle (but scope depends on type).
- 3 common type
  - emptyDir
  - hostPath
  - PersistentVolume (PV) + PersistentVolumeClaim (PVC)



 


---

Example

<div grid grid-cols-2>

```yml
apiVersion: v1
kind: Pod
metadata:
  name: fortune
spec:
  containers:
    - name: html-generator
      image: luksa/fortune
      volumeMounts:
        - name: html 
          mountPath: /var/htdocs
  volumes: # define volumes
    - name: html # name of the volumes
      emptyDir: {} # define type is emptyDir

```

```yml
apiVersion: v1
kind: Pod
metadata:
  name: hostpath-volume
spec:
  containers:
    - image: nginx:alpine
      name: web-server
      volumeMounts:
        - name: html
          mountPath: /usr/share/nginx/html
          readOnly: true
        - name: log # log volume
          mountPath: /var/log/nginx # mounted at /var/log/nginx in the container
      ports:
        - containerPort: 80
          protocol: TCP
  volumes:
    - name: log
      hostPath: # hostPath volume
        path: /var/log # folder of woker node

```
</div>



---
  
<div grid grid-cols-2>

<div>
PV 

- Cluster-level storage resource (created by admin)

- Represents real storage: cloud disk (AWS EBS, GCP PD, Azure Disk) or on-prem (NFS, Ceph, local)

- Independent of Pod lifecycle (data survives pod restart/delete)
</div>

<div>
PVC 

- A request for storage by a developer/application

- Defines how much storage + access mode needed

- Kubernetes matches PVC → PV and binds automatically
</div>

</div>

<img src="/pvName.png" width="500px" />

---

```yml

apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: mongodb-pvc
spec:
  resources:
    requests:
      storage: 10Gi # request 10Gi storage
  accessModes:
    - ReadWriteOnce # only allow one node can be read and write

```



---
