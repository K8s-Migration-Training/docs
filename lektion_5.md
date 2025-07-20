---
title: Lektion 5 - Erster Workload in der Cloud
layout: home
---

Verbindung mit AKS herstellen

```bash
   az aks get-credentials --resource-group rg-mg-k8s-training --name aks-mg-k8s-training
```

Helm installieren auf dem Windows Host

```bash
   choco install kubernetes-helm
```

Ingress Controller installieren

```bash
   helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
   helm repo update

   helm install nginx-ingress ingress-nginx/ingress-nginx --namespace ingress-nginx --create-namespace --set controller.service.externalTrafficPolicy=Local
```

Keycloak installieren

```bash
   helm repo add bitnami https://charts.bitnami.com/bitnami
   helm install keycloak bitnami/keycloak --set auth.adminUser=admin --set auth.adminPassword=admin --set service.type=ClusterIP
```

Kurz warten
