---
title: Lektion 1 - Einführung & Zielsetzung
layout: home
---

Lernziel: Du verstehst die Gesamtmotivation und das Ziel der Migration, kennst du grundlegenden Unterschiede zwischen On-Prem und Cloud Kubernetes und die Wirtschaftliche Bedeutung einer Migration

1. Ausgangssituation und Motivation
   Kubernetes hat sich in den letzten Jahren als De-facto-Standard für den Betrieb containerisierter Anwendungen etabliert. Viele Unternehmen betreiben ihre Kubernetes-Cluster derzeit noch in eigenen Rechenzentren oder auf virtuellen Maschinen in selbstverwalteten Umgebungen. Mit dem zunehmenden Bedarf an Skalierbarkeit, Ausfallsicherheit und Automatisierung gewinnen Managed Kubernetes-Dienste wie Azure Kubernetes Service (AKS) zunehmend an Bedeutung. AKS bietet ein vollständig verwaltetes Control Plane, tiefe Integration in das Azure-Ökosystem und standardisierte Sicherheits- und Netzwerkfunktionen, alles Aspekte, die den operativen Aufwand erheblich reduzieren und die Innovationsgeschwindigkeit erhöhen können.

   Eine Migration in die Cloud ist jedoch weit mehr als ein reiner Infrastrukturwechsel. Sie bringt tiefgreifende Veränderungen mit sich: Anwendungen müssen angepasst, Konfigurationen überarbeitet und Prozesse neugestaltet werden. Gleichzeitig erwarten Unternehmen von einer Migration ein hohes Maß an Stabilität, Sicherheit und Effizienz. Genau hier setzt die Standardisierung an – durch die Definition wiederholbarer, getesteter und dokumentierter Migrationspfade soll sichergestellt werden, dass Migrationen strukturiert, kontrolliert und nachvollziehbar durchgeführt werden können.

2. Herausforderungen bei der Migration
   Die Migration eines Kubernetes-Clusters in die Cloud ist kein einfacher „Lift & Shift“-Prozess. Zu den häufigsten Herausforderungen zählen Unterschiede in den Kubernetes-Versionen, inkompatible APIs oder CRDs, veränderte Netzwerkarchitekturen, sowie nicht migrierbare Ressourcen wie persistente Volumes oder spezifische Storage-Treiber. Auch betriebsspezifische Eigenheiten wie CI/CD-Pipelines, Logging- und Monitoringlösungen oder interne Zertifikatsstrukturen müssen berücksichtigt und angepasst werden.

   Ein weiterer kritischer Aspekt ist die Sicherheit: Konfigurationen, die in der On-Prem-Umgebung tolerierbar waren, sind in der Cloud mitunter nicht mehr zulässig oder sicher. Zudem verändert sich das Rollen- und Berechtigungskonzept durch die Azure-Integration grundlegend. Ohne einheitliche Standards kann eine Migration schnell zu inkonsistenten Zuständen führen, die schwer wartbar sind.

3. Wirtschaftliche Bedeutung
