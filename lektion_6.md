---
title: Lektion 6 - Erster Workload in der Cloud
layout: home
---

Lernziel: Migration eines bestehenden Frontend-Microservices in ein Azure Kubernetes Service (AKS) Cluster mit externer Erreichbarkeit und OAuth2-Authentifizierung via Azure Entra ID.

## Schritte zur Migration

```bash
az login
az aks get-credentials \
  --resource-group rg-mg-k8s-training \
  --name aks-mg-k8s-training
```

Verwende die bestehenden YAML-Dateien:

```bash
kubectl apply -f frontend-service.yaml
kubectl apply -f frotend-deployment.yaml
```

Ingress Controller installieren

```bash
helm install nginx-ingress ingress-nginx/ingress-nginx \
  --namespace ingress-nginx \
  --create-namespace \
  --set controller.service.type=LoadBalancer
```

Öffentliche IP mit DNS verknüpfen
Azure-Portal -> Öffentliche IP-Adressen
IP-Adresse des Ingress Controllers auswählen
Unter Konfiguration einen DNS-Namen vergeben

OAuth2-Proxy bereitstellen
Azure App-Registrierung
Azure-Portal → App-Registrierungen

Neue Registrierung mit Redirect-URL: https://<DOMAIN>/oauth2/callback

Client-ID, Tenant-ID notieren

Client-Secret unter Zertifikate & Geheimnisse erstellen

```bash
openssl rand -base64 32
```

Deployment erstellen oauth2-proxy.yaml

Service definieren oauth2-proxy-service.yaml

Ingress-Ressourcen definieren

Route /oauth2 für Authentifizierung:

```bash
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: oauth2-proxy-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx
  rules:
    - http:
        paths:
          - path: /oauth2
            pathType: Prefix
            backend:
              service:
                name: oauth2-proxy
                port:
                  number: 4180
```

Frontend-Ingress mit OAuth2-Schutz

```bash
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
    nginx.ingress.kubernetes.io/auth-url: "http://<EXTERNAL-IP>/oauth2/auth"
    nginx.ingress.kubernetes.io/auth-signin: "http://<EXTERNAL-IP>/oauth2/start?rd=$request_uri"
spec:
  ingressClassName: nginx
  rules:
    - http:
        paths:
          - path: /frontend
            pathType: Prefix
            backend:
              service:
                name: frontend
                port:
                  number: 80
```

Ergebnis
Der Frontend-Service ist unter /frontend erreichbar und über OAuth2 via Azure Entra ID abgesichert.

Weitere Aufgaben: migriere noch den Event- und Ticketservice

[Link zur Umfrage]
