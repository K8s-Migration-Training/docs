---
title: Lektion 8 - Migration der Monitoring Lösung
layout: home
---

Lernziel: Du richtest in deinem AKS-Cluster ein Monitoring-System mit Prometheus und Grafana ein.

Stelle sicher, dass du Folgendes hast:

- Zugriff auf deinen AKS-Cluster (`kubectl` konfiguriert)
- Helm ist installiert: `helm version`

Aufgabe 1: Prometheus installieren

Verwende Helm, um Prometheus zu installieren.

Todos: Finde heraus, wie du das Helm-Repo hinzufügst
Installiere Prometheus im Namespace monitoring.
Überprüfe, ob die Pods laufen.
Greife auf die Prometheus UI zu – wie?

Aufgabe 2: Grafana installieren
Installiere Grafana über Helm im Namespace monitoring.
Finde das Admin-Login heraus.
Greife auf die UI zu
Füge Prometheus als Datenquelle in Grafana hinzu

Teste dein Monitoring-Setup

[Link zur Umfrage]
