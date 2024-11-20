# Architekturübersicht

## Einführung

Die SnippetLibrary wurde als moderne, skalierbare Webanwendung konzipiert, die es Entwicklern ermöglicht, Code-Snippets effizient zu verwalten und zu teilen. Die Architektur basiert auf bewährten Technologien und Best Practices, um eine wartbare und erweiterbare Codebasis zu gewährleisten.

## Systemarchitektur

Unsere Anwendung folgt einer klassischen Client-Server-Architektur mit einer klaren Trennung von Frontend und Backend. Diese Trennung ermöglicht es uns, beide Komponenten unabhängig voneinander zu entwickeln und zu skalieren.

### Frontend

Das Frontend wurde mit Angular 18 entwickelt und bietet eine reactive Single Page Application (SPA). Wir haben uns für Angular entschieden, da es:

- Ein robustes Framework für enterprise Anwendungen bietet
- Hervorragende TypeScript-Integration besitzt
- Umfangreiche Testing-Möglichkeiten bereitstellt
- Eine große, aktive Community hat

Die Benutzeroberfläche nutzt Angular Material und PrimeNG für ein konsistentes, modernes Design. Besonders hervorzuheben ist die Integration von PrismJS für das Syntax-Highlighting, das eine Vielzahl von Programmiersprachen unterstützt.

### Backend

Das Backend basiert auf FastAPI, einem modernen, schnellen Python-Framework für API-Entwicklung. Die Wahl fiel auf FastAPI aufgrund:

- Hervorragender Performance
- Automatischer API-Dokumentation
- Einfacher Async/Await Unterstützung
- Type Hints und Validierung

Die Datenpersistenz wird durch eine MySQL-Datenbank gewährleistet, die sich besonders gut für strukturierte Daten wie Code-Snippets eignet.

## Datenmodell und Beziehungen

Das zentrale Element unserer Anwendung ist das Snippet-Modell. Ein Snippet repräsentiert einen wiederverwendbaren Code-Block mit zusätzlichen Metadaten.

## Sicherheitskonzept

Die Sicherheit der Anwendung basiert auf mehreren Säulen:

1. **Authentifizierung**
   Azure Active Directory (AAD) dient als Identity Provider und ermöglicht Single Sign-On (SSO). Dies vereinfacht die Benutzerverwaltung erheblich und bietet enterprise-grade Sicherheit.

2. **Autorisierung**
   Ein granulares Berechtigungssystem steuert den Zugriff auf Snippets und Funktionen. Die Implementierung erfolgt sowohl auf API- als auch auf UI-Ebene.

3. **Datensicherheit**
   Alle Kommunikation erfolgt verschlüsselt über HTTPS. Die Datenbank-Zugriffe sind durch Prepared Statements gegen SQL-Injection geschützt.

## Performance-Optimierung

Unsere Architektur berücksichtigt Performance-Aspekte auf mehreren Ebenen:

### Frontend-Optimierungen
- Lazy Loading von Modulen reduziert die initiale Ladezeit
- Virtual Scrolling für große Listen verhindert Performance-Einbrüche
- Intelligentes Caching von Snippets minimiert Server-Anfragen

### Backend-Optimierungen
- Connection Pooling für effiziente Datenbankzugriffe
- Caching häufig angefragter Daten
- Asynchrone Verarbeitung wo möglich

## Entwicklungsworkflow

Der Entwicklungsprozess wurde mit Fokus auf Effizienz und Qualität gestaltet:

1. **Lokale Entwicklung**
   - Hot Reload für schnelles Feedback
   - Umfangreiche Debug-Konfiguration
   - Automatisierte Tests

2. **Deployment Pipeline**
   