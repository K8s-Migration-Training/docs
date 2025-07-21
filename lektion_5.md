---
title: Lektion 5 - Erster Workload in der Cloud
layout: home
---

Lernziel: In dieser Lektion lernst du, wie du deinen ersten Service und Deployment in AKS erstellt.

Dokumentation zu Kubernetes Service:
[Service](https://kubernetes.io/docs/concepts/services-networking/service/)

Dokumentation zu Kubernetes Deployments:
[Deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)

Verbindung mit AKS herstellen

```bash
   az aks get-credentials --resource-group rg-mg-k8s-training --name aks-mg-k8s-training
```

Bevor du fortfährst, stelle sicher, dass du mit AKS verbunden bist

```bash
   az aks get-credentials --resource-group {ressource_group} --name {cluster_name}
```

Erstelle eine neue Datei nginx-deployment.yaml mit folgendem Inhalt:

```bash
   apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 2
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

Und führe das deployment aus:

```bash
kubectl apply -f nginx-deployment.yaml
```

Erstelle nun einen Service

```bash
apiVersion: v1
kind: Service
metadata:
  name: nginx-service
spec:
  type: LoadBalancer
  selector:
    app: nginx
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

Und wende das Deployment an:

```bash
kubectl apply -f nginx-service.yaml
```

Jetzt erstellt AKS automatisch eine öffentliche IP-Adresse für deinen NGINX-Service.

```bash
kubectl get service nginx-service
```

Warte ein bis alles hochgefahren ist und prüfer ob alles über deinen Browser erreichbar ist.

[Link zur Umfrage]
