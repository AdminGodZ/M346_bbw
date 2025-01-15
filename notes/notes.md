# Cloud Computing und Virtualisierung - Komplette Übersicht

## Einleitung
Dieses Dokument basiert auf dem Modul 346 - Cloud Lösungen konzipieren und realisieren von ICT-Berufsbildung. Die Lernziele sind im Zusammenhang mit der Entwicklung der Fach- und Methodenkompetenz zu verstehen.

## 1. Virtualisierung

*Lernziel: Sie können den Begriff der "Virtualisierung" erläutern.*

### Was ist Virtualisierung?
Virtualisierung ist eine Technologie, die es ermöglicht, physische Computerhardware in mehrere virtuelle Instanzen aufzuteilen. Stellen Sie sich einen leistungsstarken Computer vor, der wie mehrere separate Computer funktioniert. Jede dieser virtuellen Instanzen verhält sich wie ein eigenständiger Computer mit eigenem Betriebssystem, Speicher und Netzwerkzugang.

#### Praktisches Beispiel:
Ein physischer Server mit 32GB RAM und 8 CPU-Kernen könnte in vier virtuelle Server aufgeteilt werden, jeder mit 8GB RAM und 2 CPU-Kernen. Jeder dieser virtuellen Server kann ein anderes Betriebssystem laufen lassen und unterschiedliche Aufgaben erfüllen.

#### Vorteile:
- **Ressourceneffizienz**: Bessere Auslastung der Hardware
- **Isolation**: Probleme in einem virtuellen System beeinflussen andere nicht
- **Flexibilität**: Schnelles Erstellen, Kopieren und Löschen von Systemen
- **Kosteneinsparung**: Weniger physische Hardware nötig
- **Disaster Recovery**: Einfacheres Backup und Wiederherstellung

### Hypervisor

*Lernziel: Sie können grob erklären welche Rolle ein "Hypervisor" in der Virtualisierung spielt.*

Der Hypervisor ist das Herzstück der Virtualisierung - er ist die Software, die die Virtualisierung überhaupt erst möglich macht. Man kann ihn sich als "Dirigenten" vorstellen, der die physischen Ressourcen an die virtuellen Maschinen verteilt und überwacht.

#### Hauptaufgaben des Hypervisors:
1. **Ressourcenverwaltung**: 
   - Verteilt CPU, RAM und Speicher an virtuelle Maschinen
   - Stellt sicher, dass jede VM ihre zugewiesenen Ressourcen erhält
   - Verhindert Ressourcenkonflikte zwischen VMs

2. **Isolation**: 
   - Trennt virtuelle Maschinen voneinander
   - Verhindert, dass Probleme einer VM andere beeinflussen
   - Gewährleistet Sicherheit zwischen VMs

3. **Hardware-Abstraktion**:
   - Präsentiert virtuelle Hardware an VMs
   - Übersetzt VM-Anfragen in physische Hardware-Befehle
   - Ermöglicht Hardware-Unabhängigkeit

*Lernziel: Sie kennen den Unterschied zwischen Typ 1 und Typ 2 Hypervisors und können den auch erklären.*

#### Hypervisor-Typen:

1. **Typ 1 Hypervisor (Bare-Metal)**
   - Läuft direkt auf der Hardware
   - Kein zusätzliches Betriebssystem nötig
   - Höhere Leistung und Effizienz
   - Beispiele: 
     * VMware ESXi
     * Microsoft Hyper-V
     * Citrix XenServer
   - Typischer Einsatz: Rechenzentren, Enterprise-Server

2. **Typ 2 Hypervisor (Hosted)**
   - Läuft als Programm auf einem Betriebssystem
   - Einfachere Installation und Bedienung
   - Geringere Leistung als Typ 1
   - Beispiele:
     * VirtualBox
     * VMware Workstation
     * Parallels Desktop
   - Typischer Einsatz: Entwicklung, Testing, Desktop-Virtualisierung

### Hyperscaler

*Lernziel: Sie können den Begriff "Hyperscaler" erklären im Zusammenhang mit Cloud-Systemen.*

Hyperscaler sind Unternehmen, die massive, skalierbare Cloud-Computing-Infrastrukturen betreiben. Sie zeichnen sich durch folgende Eigenschaften aus:

#### Charakteristiken:
1. **Massive Skalierung**:
   - Können innerhalb von Minuten tausende Server bereitstellen
   - Globale Infrastruktur mit mehreren Rechenzentren
   - Automatische Skalierung nach Bedarf

2. **Technologische Innovation**:
   - Entwickeln eigene Hardware und Software
   - Setzen Standards in der Industrie
   - Kontinuierliche Innovation und Verbesserung

3. **Geschäftsmodell**:
   - Pay-as-you-go Preismodell
   - Elastische Ressourcennutzung
   - Globale Verfügbarkeit

#### Beispiele für Hyperscaler:
- Amazon Web Services (AWS)
- Microsoft Azure
- Google Cloud Platform (GCP)
- Alibaba Cloud

## 2. Cloud-System Schichten

*Lernziel: Sie kennen Schichten von Cloud-Systemen.*

### Infrastructure as a Service (IaaS)
Die unterste Schicht der Cloud-Services. Hier erhalten Sie:
- Virtuelle Maschinen
- Speicherplatz
- Netzwerkkomponenten
- Maximale Kontrolle über die Infrastruktur

**Beispiel**: AWS EC2, wo Sie virtuelle Server mit selbst gewähltem Betriebssystem erstellen können.

### Platform as a Service (PaaS)
Die mittlere Schicht, die auf IaaS aufbaut:
- Entwicklungsumgebungen
- Datenbanken
- Middleware
- Weniger Verwaltungsaufwand für Infrastruktur

**Beispiel**: Google App Engine, wo Sie Ihre Anwendung deployen können, ohne sich um die darunterliegende Infrastruktur zu kümmern.

### Software as a Service (SaaS)
Die oberste Schicht, die auf PaaS aufbaut:
- Fertige Anwendungen
- Keine Installation nötig
- Zugriff über Browser
- Minimaler Verwaltungsaufwand

**Beispiel**: Microsoft 365, das komplette Office-Paket im Browser.

### Function as a Service (FaaS)
Eine spezielle Form des Cloud Computing:
- Serverlose Architektur
- Ereignisgesteuerte Ausführung
- Automatische Skalierung
- Bezahlung nur für tatsächliche Ausführung

**Beispiel**: AWS Lambda, wo Code nur bei bestimmten Ereignissen ausgeführt wird.

## 3. Betriebsmodelle

*Lernziel: Sie kennen die drei Betriebsmodelle und können Sie erklären.*

### Public Cloud
- Öffentlich zugängliche Cloud-Ressourcen
- Shared Infrastructure (geteilte Ressourcen)
- Hohe Skalierbarkeit
- Geringere Kosten durch Ressourcenteilung
- Beispiele: AWS, Google Cloud

### Private Cloud
- Dedizierte Cloud-Ressourcen für eine Organisation
- Volle Kontrolle über Infrastruktur
- Höhere Sicherheit und Compliance-Möglichkeiten
- Typischerweise höhere Kosten
- Beispiel: Firmeneigenes Rechenzentrum mit OpenStack

### Hybrid Cloud
- Kombination aus Public und Private Cloud
- Flexible Ressourcenverteilung
- Sensitive Daten in Private Cloud
- Skalierbare Workloads in Public Cloud
- Beispiel: Kernsysteme on-premise, Webseite in Public Cloud

## 4. Cloud-Migrationsmodelle

*Lernziel: Sie kennen die Begriffe der Migrationsmodellen und deren Zielplattformen.*

### Rehosting (Lift & Shift)
- Direkte Migration ohne große Änderungen
- Schnelle Implementation
- Geringste Anpassungen nötig
- Beispiel: VM-Migration von On-Premise zu AWS EC2

### Refactoring
- Codeoptimierung für Cloud
- Nutzung von Cloud-native Features
- Moderate Anpassungen
- Beispiel: Anpassung einer App für Container

### Rearchitecting
- Komplette Neugestaltung der Architektur
- Maximale Cloud-Vorteile
- Hoher initialer Aufwand
- Beispiel: Monolith zu Microservices

### Rebuild
- Komplette Neuentwicklung
- Cloud-native von Grund auf
- Höchster Aufwand
- Beispiel: Legacy-System neu als Cloud-native App

## 5. Speichermodelle

*Lernziel: Sie kennen die vier Speichermodelle und deren Einsatzgebiete.*

### Block Storage
- Persistenter Speicher
- Hohe Performance
- Direkte Festplattensimulation
- Beispiel: AWS EBS für Datenbanken

### Object Storage
- Hochskalierbar
- Kostengünstig
- Ideal für statische Dateien
- Beispiel: AWS S3 für Backups

### File Storage
- Hierarchische Struktur
- Gemeinsamer Zugriff
- Traditionelles Dateisystem
- Beispiel: AWS EFS für gemeinsame Dokumente

### Ephemeral Storage
- Temporärer Speicher
- An VM-Lifecycle gebunden
- Hohe Performance
- Beispiel: EC2 Instance Store

*Lernziel: Sie kennen den Unterschied zwischen persistentem und flüchtigem Speicher.*

#### Persistenter Speicher:
- Daten bleiben nach Neustart erhalten
- Unabhängig von VM-Lifecycle
- Wichtig für dauerhafte Datenspeicherung
- Beispiel: Datenbanken, Benutzerprofile

#### Flüchtiger Speicher:
- Daten verschwinden nach Neustart
- An VM-Lifecycle gebunden
- Ideal für temporäre Daten
- Beispiel: Cache, Session-Daten

## 6. Netzwerk und Sicherheit

*Lernziel: Sie kennen die Netzwerkbegriffe und können diese erklären.*

### Netzwerkkonzepte
1. **VPC (Virtual Private Cloud)**
   - Isoliertes virtuelles Netzwerk
   - Eigener IP-Adressbereich
   - Sicherheitskontrolle
   - Beispiel: AWS VPC für Unternehmensanwendungen

2. **Subnet**
   - Unterteilung eines VPC
   - Verschiedene Sicherheitszonen
   - Public/Private Bereiche
   - Beispiel: Trennung von Web- und Datenbankservern

3. **Netzwerkinterface**
   - Verbindung zur virtuellen Netzwerkkarte
   - IP-Konfiguration
   - Sicherheitsgruppen
   - Beispiel: Elastic Network Interface in AWS

*Lernziel: Sie kennen den Unterschied zwischen einer IP und einem IP-Range.*

#### IP vs IP-Range:
- **Einzelne IP**: 
  * Spezifische Adresse (z.B. 192.168.1.1)
  * Identifiziert einzelnen Host
  * Beispiel: Server-IP

- **IP-Range**: 
  * Adressbereich (z.B. 192.168.1.0/24)
  * CIDR-Notation
  * Definiert Netzwerksegment
  * Beispiel: Subnetz-Definition

*Lernziel: Sie kennen die wichtigsten Ports und ihre Verwendung.*

### Wichtige Ports
- **Port 22**: SSH (Secure Shell)
  * Sichere Fernwartung
  * Kommandozeilen-Zugriff
  * Standardport für Linux-Administration

- **Port 80**: HTTP
  * Unverschlüsselter Webverkehr
  * Standard-Webseiten
  * Oft weitergeleitet zu HTTPS

- **Port 443**: HTTPS
  * Verschlüsselter Webverkehr
  * Sichere Webseiten
  * SSL/TLS Verschlüsselung

- **Port 3306**: MySQL
  * Datenbankzugriff
  * Standard MySQL-Port
  * Oft nur intern zugänglich

## 7. Cloud-init

*Lernziel: Sie kennen die Grundelemente von YAML und Cloud-init.*

### YAML Grundlagen
- Menschenlesbare Syntax
- Schlüssel-Wert Paare
- Listen und Verschachtelungen
- Einrückung wichtig

### Cloud-init Funktionen
1. **Systemkonfiguration**:
   ```yaml
   #cloud-config
   packages:
     - nginx
     - mysql-server
   ```

2. **Benutzer-Management**:
   ```yaml
   users:
     - name: webadmin
       sudo: ALL=(ALL) NOPASSWD:ALL
       ssh_authorized_keys:
         - ssh-rsa AAAA...
   ```

3. **Skript-Ausführung**:
   ```yaml
   runcmd:
     - systemctl start nginx
     - mysql_secure_installation
   ```

*Lernziel: Sie kennen den Begriff "Infrastructure As Code".*

### Infrastructure as Code (IaC)
- Infrastruktur als Code definiert
- Versionierbar
- Reproduzierbar
- Automatisierbar

#### Populäre IaC Tools:
1. **Terraform**
   - Cloud-übergreifend
   - Deklarative Syntax
   - Große Community

2. **AWS CloudFormation**
   - AWS-spezifisch
   - JSON/YAML Templates
   - Tiefe AWS-Integration

3. **Azure Resource Manager**
   - Azure-spezifisch
   - JSON Templates
   - Azure-Integration

4. **Ansible**
   - Konfigurationsmanagement
   - YAML-basiert
   - Agentenlos
