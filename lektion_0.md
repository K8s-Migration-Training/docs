---
title: Lektion 0 - Installation des On-Premises Clusters
layout: home
---

Lernziel: In dieser Lektion lernst du, wie du mit Vagrant das On-Premises Cluster lokal auf deinem Computer aufsetzt, welches später in die Cloud migriert werden soll.

Klone zunächst das folgende Cluster:

[Zum Repository](https://github.com/K8s-Migration-Training/infrastructure)

### Voraussetzungen

Für die lokale Installation benötigst du:

- Windows 11 Pro
- Vagrant
- Aktiviertes Hyper-V

Wie du Hyper-V aktivierst, findest du [Hier](https://learn.microsoft.com/de-de/windows-server/virtualization/hyper-v/get-started/install-hyper-v?tabs=powershell&pivots=windows)

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

5. Verbinde dich nur mit dem Kubernetes Cluster und führe die folgende Datei aus:

```bash
   vagrant ssh master
   sudo /shared/runmanifest.sh
   sudo /shared/monitoring.sh
```
