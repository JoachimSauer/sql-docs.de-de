---
title: "Datenbank-E-Mail-Protokoll und -&#220;berwachung | Microsoft Docs"
ms.custom: ""
ms.date: "03/06/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Überwachen [SQL Server]"
  - "Datenbank-E-Mail [SQL Server], überwachen"
  - "Protokolle [Datenbank-E-Mail]"
  - "Überwachungen [SQL Server], Datenbank-E-Mail"
  - "Datenbank-E-Mail [SQL Server], protokollieren"
ms.assetid: 846589ee-5fe5-4ab3-b335-0c253e569f99
caps.latest.revision: 30
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 30
---
# Datenbank-E-Mail-Protokoll und -&#220;berwachung
  Die Protokollierungsfunktionalität für Datenbank-E-Mail stellt eine Möglichkeit zum Isolieren und Beheben von Problemen dar. Datenbank-E-Mail speichert die Protokollinformationen in der **msdb** -Datenbank. Informationen zum E-Mail-Inhalt, E-Mail-Status und zu empfangenen Nachrichten, z. B. Fehler, in Datenbank-E-Mail werden von Datenbank-E-Mail protokolliert und können zur Problembehebung und Überwachung verwendet werden.  
  
## Protokolle zu Datenbank-E-Mail  
 In den Protokollinformationen der **msdb** -Datenbank von [Database Mail External Program](../../relational-databases/database-mail/database-mail-external-program.md)vorhandene Tabellen. [Datenbank-E-Mail-Sichten &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/database-mail-views-transact-sql.md) machen die Tabellen für die Problembehandlung verfügbar. Fehler werden in der Sicht [sysmail_event_log &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sysmail-event-log-transact-sql.md) aufgeführt, wenn der Service Broker das externe Programm nicht aktivieren kann, wenn im externen Programm Netzwerkfehler auftreten, oder wenn der SMTP-Server (Simple Mail Transport Protocol) eine E-Mail-Nachricht verweigert. Wenn sich das externe Programm nicht bei der **msdb** -Tabelle anmelden kann, werden vom Programm Fehler im Windows-Anwendungsereignisprotokoll protokolliert.  
  
 Interne Tabellen der **msdb**-Datenbank enthalten die E-Mail-Nachrichten aus der Datenbank-E-Mail sowie den aktuellen Status der einzelnen Nachrichten. Datenbank-E-Mail aktualisiert diese Tabellen bei der Verarbeitung jeder Meldung.  
  
## Überwachungstasks von Datenbank-E-Mail  
  
|||  
|-|-|  
|**Überprüfen und Verwalten von Protokollen zu Datenbank-E-Mail**|**Link zum Thema**|  
|Überprüfen des Übermittlungsstatus einer einzelnen Nachricht|[Überprüfen des Status von mit Datenbank-E-Mail gesendeten E-Mail-Nachrichten](../../relational-databases/database-mail/check-the-status-of-e-mail-messages-sent-with-database-mail.md)|  
|Bereinigen von Nachrichten, Anlagen und Protokolleinträgen in Datenbank-E-Mail|[sysmail_delete_mailitems_sp &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-delete-mailitems-sp-transact-sql.md)<br /><br /> [sysmail_delete_log_sp &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sysmail-delete-log-sp-transact-sql.md)|  
|Archivieren der Nachrichten und Protokolle in Datenbank-E-Mail|[Erstellen eines Auftrags des SQL Server-Agents zum Archivieren von Datenbank-E-Mail-Nachrichten und Ereignisprotokollen](../../relational-databases/database-mail/create-a-sql-server-agent-job-to-archive-database-mail-messages-and-event-logs.md)|  
  
## Siehe auch  
 [Überwachen der Ressourcenverwendung &#40;Systemmonitor&#41;](../../relational-databases/performance-monitor/monitor-resource-usage-system-monitor.md)  
  
  