---
title: Lektion 0
layout: home
---

Um ein Kubernetes-Cluster lokal aufzusetzen, das du später in die Cloud migrieren kannst, klone bitte das folgende Repository:

[Zum Repository](https://github.com/K8s-Migration-Training/infrastructure)

### Voraussetzungen

Für die lokale Installation benötigst du:

- Windows 11 Pro
- Vagrant
- Aktiviertes Hyper-V

### Installation

1. Öffne ein Terminal oder die Konsole **als Administrator**.
2. Navigiere in das Infrastrukturverzeichnis:

   ```bash
   cd ../infrastructure
   ```

3. Starte nun die VMs mit Vagrant.

```bash
   vagrant up --provider=hyperv
```

4. Gib deinen Windows-Benutzernamen und dein Passwort ein, falls danach gefragt wird.

### Vorbereitung für die Cloud-Migration

Für die spätere Migration in die Cloud benötigst du eine Azure Subscription. Du kannst dir eine hier einrichten:
https://azure.microsoft.com/en-us
