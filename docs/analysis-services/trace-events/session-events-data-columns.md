---
title: "Datenspalten f&#252;r Sitzungsereignisse | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "Sitzungsereignisse (Ereigniskategorie)"
ms.assetid: 35853451-6768-4a02-8b8f-81a8ae37a333
caps.latest.revision: 21
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 21
---
# Datenspalten f&#252;r Sitzungsereignisse
  Die Sitzungsereignisse-Ereigniskategorie weist folgende Ereignisklasse auf:  
  
|**Ereignis-ID**|**Ereignisname**|**Ereignisbeschreibung**|  
|------------------|--------------------|---------------------------|  
|41|Existing Connection|Vorhandene Benutzerverbindung.|  
|42|Vorhandene Sitzung|Vorhandene Sitzung.|  
|43|Sitzungsinitialisierung|Sitzungsinitialisierung.|  
  
 In der folgenden Tabelle sind die Datenspalten für diese Ereignisklasse aufgeführt.  
  
## Existing Connection  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|NTUserName|32|8|Windows-Benutzername.|  
|NTDomainName|33|8|Windows-Domäne, zu der der Benutzer gehört.|  
|ClientHostName|35|8|Der Name des Computers, auf dem der Client ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Hostname durch den Client bereitgestellt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|ApplicationName|37|8|Der Name der Clientanwendung, die die Verbindung mit dem Server hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|  
|SPID|41|1|Serverprozess-ID. Hierdurch wird eine Benutzersitzung eindeutig gekennzeichnet. Dies entspricht direkt dem von XML/A verwendeten Sitzungs-GUID.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
  
## Vorhandene Sitzung  
  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|---------------------|-------------------|---------------------|----------------------------|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|Dauer|5|2|Die Zeit (in Millisekunden), die für das Ereignis benötigt wurde.|  
|CPUTime|6|2|Die CPU-Zeit (in Millisekunden), die vom Ereignis verwendet wurde.|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|NTUserName|32|8|Windows-Benutzername.|  
|NTDomainName|33|8|Windows-Domäne, zu der der Benutzer gehört.|  
|ClientHostName|35|8|Der Name des Computers, auf dem der Client ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Hostname durch den Client bereitgestellt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|ApplicationName|37|8|Der Name der Clientanwendung, die die Verbindung mit dem Server hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|  
|NTCanonicalUserName|40|8|Benutzername in kanonischer Form. Zum Beispiel "engineering.microsoft.com/software/someone".|  
|SPID|41|1|Serverprozess-ID. Hierdurch wird eine Benutzersitzung eindeutig gekennzeichnet. Dies entspricht direkt dem von XML/A verwendeten Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
|RequestProperties|45|9|XMLA-Anforderungseigenschaften.|  
  
## Sitzungsinitialisierung  
  
|||||  
|-|-|-|-|  
|**Spaltenname**|**Spalten-ID**|**Spaltentyp**|**Spaltenbeschreibung**|  
|CurrentTime|2|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|StartTime|3|5|Der Zeitpunkt, zu dem das Ereignis begonnen hat (falls verfügbar). Für das Filtern lauten die erwarteten Formate "JJJJ-MM-TT" und "JJJJ-MM-TT HH:MM:SS".|  
|ConnectionID|25|1|Eindeutige Verbindungs-ID.|  
|DatabaseName|28|8|Name der Datenbank, in der die Anweisung des Benutzers ausgeführt wird.|  
|NTUserName|32|8|Windows-Benutzername.|  
|NTDomainName|33|8|Windows-Domäne, zu der der Benutzer gehört.|  
|ClientHostName|35|8|Der Name des Computers, auf dem der Client ausgeführt wird. Diese Datenspalte wird aufgefüllt, wenn der Hostname durch den Client bereitgestellt wird.|  
|ClientProcessID|36|1|Die Prozess-ID der Clientanwendung.|  
|ApplicationName|37|8|Der Name der Clientanwendung, die die Verbindung mit dem Server hergestellt hat. Diese Spalte wird mit den Werten aufgefüllt, die von der Anwendung übergeben werden, und nicht mit dem angezeigten Namen des Programms.|  
|NTCanonicalUserName|40|8|Benutzername in kanonischer Form. Zum Beispiel "engineering.microsoft.com/software/someone".|  
|SPID|41|1|Serverprozess-ID. Hierdurch wird eine Benutzersitzung eindeutig gekennzeichnet. Dies entspricht direkt dem von XML/A verwendeten Sitzungs-GUID.|  
|TextData|42|9|Dem Ereignis zugeordnete Textdaten.|  
|ServerName|43|8|Name des Servers, der das Ereignis erzeugt.|  
|RequestProperties|45|9|XMLA-Anforderungseigenschaften.|  
  
## Siehe auch  
 [Sicherheitsüberwachung-Ereigniskategorie](../../analysis-services/trace-events/security-audit-event-category.md)  
  
  