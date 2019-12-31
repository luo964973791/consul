### helm3.0部署consul,提前准备三个nfs

```
vi pv0.yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: consul-0
spec:
  capacity:
    storage: 1Gi
  accessModes: ["ReadWriteOnce"]
  #storageClassName: consul-0
  nfs:
    server: 172.27.0.6
    path: "/data/consul-0"
    
    
vi pv1.yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: consul-1
spec:
  capacity:
    storage: 1Gi
  accessModes: ["ReadWriteOnce"]
  #storageClassName: consul-0
  nfs:
    server: 172.27.0.6
    path: "/data/consul-1"



vi pv2.yaml
apiVersion: v1
kind: PersistentVolume
metadata:
  name: consul-2
spec:
  capacity:
    storage: 1Gi
  accessModes: ["ReadWriteOnce"]
  nfs:
    server: 172.27.0.6
    path: "/data/consul-2"
```

### helm 安装consul

```
git clone https://github.com/luo964973791/consul.git && cd consul
helm install consul ./consul
```

