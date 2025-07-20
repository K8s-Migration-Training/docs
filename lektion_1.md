---
title: Lektion 1 - Referenzcluster auf Azure aufsetzten
layout: home
---

Lernziel: In dieser Lektion lernst du, wie du mithilfe von Terraform das vorgefertigte Referenzcluster auf Azure erstellst.

Klone zunächst das folgende Cluster:

[Zum Repository](https://github.com/K8s-Migration-Training/cloud-infrastructure)

Installiere anhand der folgenden Einleitung die Azure CLI:

[Azure CLI](https://learn.microsoft.com/de-de/cli/azure/install-azure-cli?view=azure-cli-latest)

Führe nun den folgenden Befehl aus und melde dich an deiner Azure subscription an:

```bash
   az login
```

Falls Terraform noch nicht auf deinem System installiert ist, folge der offiziellen Anleitung:

[Terraform installieren](https://developer.hashicorp.com/terraform/downloads)

Überprüfe anschließend, ob Terraform korrekt installiert wurde:

```bash
   terraform -v
```

Initialisiere Terraform im Projektverzeichnis:

```bash
   terraform init
```

Jetzt kannst du das Cluster mit den folgenden Befehlen erstellen:

```bash
   terraform plan
   terraform apply
```

Nach der erfolgreichen Erstellung kannst du die Kubernetes-Konfiguration abrufen:

```bash
   az aks get-credentials --resource-group {ressource_group} --name {cluster_name}
```

Prüfe, ob dein Cluster erreichbar ist:

```bash
   kubectl get nodes
```
