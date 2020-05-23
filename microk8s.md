```
sudo snap install microk8s --classic --channel=1.18/stable 
sudo microk8s.status
microk8s.kubectl get nodes
sudo snap alias microk8s.kubectl kubectl
sudo microk8s.enable dns dashboard ingress 
sudo microk8s.kubectl proxy --accept-hosts=.* --address=0.0.0.0 & 
sudo microk8s.kubectl -n kube-system edit deploy kubernetes-dashboard -o yaml 
```
```
spec:
  progressDeadlineSeconds: 600
  replicas: 1
  revisionHistoryLimit: 10
  selector:
    matchLabels:
      k8s-app: kubernetes-dashboard
  strategy:
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
    type: RollingUpdate
  template:
    metadata:
      creationTimestamp: null
      labels:
        k8s-app: kubernetes-dashboard
    spec:
      containers:
      - args:
        - --auto-generate-certificates
        - --namespace=kube-system
        - --enable-skip-login
```

http://{IP_address}:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/

sudo microk8s.enable fluent
