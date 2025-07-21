---
title: Lektion 4 - Analyse des Ist-Zustands des On-Premises Clusters
layout: home
---

Lernziel: In dieser Lektion erfasst du den Ist-Zustand des On-Premises Cluster

1. Verbindung mit dem Cluster herstellen

Stelle zunächst eine SSH Verbindung mit der Master Node her.

```bash
   vagrant ssh master
```

2. Generelle Informationen über das Cluster

Schau dir zunächst die Version der Kubernetes Cluster an:

```bash
   kubectl version
```

Und folglich auch die Nodes die im Cluster sind:

```bash
   kubectl get nodes -o wide
```

Die Client und Server Version sind 1.28.15. Die Version ist später wichtig, wenn du das Cluster
zu Azure migrieren willst. Das Cluster sollte des Weiteren aus drei Nodes bestehen. Einer Master Node
und zwei Worker Nodes.

2. Namespaces und Workloads

```bash
   kubectl get ns
   kubectl get all -A
```

Mit dem ersten Befehl siehst du alle Namespaces im Cluster und mit dem zweitem die Zuordnung der Workloads zu
den Namespaces.

2. Deployments

```bash
   kubectl get deploy
```

Hiermit siehst du alle Deployments, welche im Cluster vorhanden sind.

Weitere Aufgaben:
Schaue dir die Microservices und die an, welche im Cluster installiert sind:
[Zum Repository](https://github.com/K8s-Migration-Training/microservice)

[Link zur Umfrage]
