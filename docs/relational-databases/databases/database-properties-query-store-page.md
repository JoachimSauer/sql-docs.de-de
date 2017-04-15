---
title: "Datenbankeigenschaften (Seite des Abfragespeichers) | Microsoft Docs"
ms.custom: ""
ms.date: "11/09/2015"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.swb.databaseproperties.querystore.f1"
ms.assetid: da47d75e-291a-4305-acef-4b0aaf5215da
caps.latest.revision: 10
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 10
---
# Datenbankeigenschaften (Seite des Abfragespeichers)
  Greifen Sie von der Prinzipaldatenbank aus auf diese Seite zu, um damit die Eigenschaften des Datenbank-Abfragespeichers zu konfigurieren und zu ändern. Diese Optionen können auch mithilfe der [ALTER DATABASE SET-Optionen](../Topic/ALTER%20DATABASE%20SET%20Options%20\(Transact-SQL\).md)konfiguriert werden. Weitere Informationen zum Abfragespeicher finden Sie unter [Monitoring Performance By Using the Query Store](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md).  
  
||  
|-|  
|**Gilt für**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] bis zur [aktuellen Version](http://go.microsoft.com/fwlink/p/?LinkId=299658)), [!INCLUDE[sqldbesa](../../includes/sqldbesa-md.md)].|  
  
## Optionen  
 Betriebsmodus  
 Gültige Werte sind OFF, READ_ONLY und READ_WRITE. OFF deaktiviert den Abfragespeicher. Im Modus READ_WRITE sammelt und speichert der Abfragespeicher Angaben zum Abfrageplan und statistische Informationen zur Laufzeitausführung. Im Modus READ_ONLY können Informationen aus dem Abfragespeicher gelesen werden, es werden jedoch keine neuen Informationen hinzugefügt. Wenn die maximale Speicherplatzbelegung des Abfragespeichers ausgelastet ist, wird der Betriebsmodus in READ_ONLY geändert.  
  
 Betriebsmodus (tatsächlich)  
 Ruft den tatsächlichen Betriebsmodus des Abfragespeichers ab.  
  
 Betriebsmodus (angefordert)  
 Ruft den gewünschten Betriebsmodus des Abfragespeichers ab und legt diesen fest.  
  
 Datenleerungsintervall (Minuten)  
 Bestimmt die Häufigkeit, mit der in den Abfragespeicher geschriebene Daten auf Datenträger gespeichert werden. Um die Leistung zu optimieren, werden durch den Abfragespeicher gesammelte Daten asynchron auf den Datenträger geschrieben. Konfiguriert die Häufigkeit, mit der diese asynchrone Übertragung auftritt.  
  
 Statistiksammlungsintervall  
 Ruft den Wert für das Statistiksammlungsintervall ab und legt diesen fest.  
  
 Maximale Größe (MB)  
 Ruft die Größe des gesamten Speicherplatzes ab, der dem Abfragespeicher zugeordnet ist, und legt diese fest.  
  
 Erfassungsmodus für den Abfragespeicher  
 -   "None" erfasst keine neue Abfragen.  
  
-   "All" erfasst alle Abfragen.  
  
-   "Auto" erfasst Abfragen basierend auf der Ressourcenbelegung.  
  
 Schwellenwert für veraltete Abfrage (Tage)  
 Ruft den Schwellenwert für veraltete Abfragen ab und legt diesen fest. Konfigurieren Sie das STALE_QUERY_THRESHOLD_DAYS-Argument, um die Anzahl der Tage anzugeben, für die Daten im Abfragespeicher beibehalten werden sollen.  
  
 Abfragedaten bereinigen  
 Entfernt den Inhalt des Abfragespeichers.  
  
 Kreisdiagramme  
 Das linke Diagramm zeigt die gesamte Nutzung der Datenbankdatei auf dem Datenträger und den Teil der Datei, der mit der Abfragespeicherdaten gefüllt ist.  
  
 Das rechte Diagramm zeigt den derzeit verbrauchten Anteil des Abfragespeicherkontingents. Beachten Sie, dass das Kontingent im linken Diagramm nicht angezeigt wird. Das Kontingent kann die aktuelle Größe der Datenbank überschreiten.  
  
## Hinweise  
 Der Abfragespeicher bietet über DBAs Einblick in die Auswahl und die Leistung des Abfrageplans. Er vereinfacht das Beheben von Leistungsproblemen, indem er das schnelle Auffinden von Leistungsabweichungen durch Änderungen an Abfrageplänen ermöglicht. Das Feature erfasst automatisch einen Verlauf der Abfrage-, Plan- und Laufzeitstatistiken und bewahrt diese zur Überprüfung auf. Es unterteilt die Daten nach Zeitfenstern und ermöglicht es Ihnen so, Verwendungsmuster für Datenbanken zu erkennen und zu verstehen, wann Abfrageplanänderungen auf dem Server aufgetreten sind. Der Abfragespeicher kann mithilfe dieser Eigenschaftenseite der Abfragespeicherdatenbank oder mithilfe der [ALTER DATABASE SET](../Topic/ALTER%20DATABASE%20SET%20Options%20\(Transact-SQL\).md) -Option konfiguriert werden. Der Abfragespeicher stellt Informationen mithilfe eines [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] -Dialogfelds dar. Weitere Informationen zum Abfragespeicher finden Sie unter [Monitoring Performance By Using the Query Store](../../relational-databases/performance/monitoring-performance-by-using-the-query-store.md).  
  
## Siehe auch  
 [Gespeicherte Prozeduren für den Abfragespeicher &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/query-store-stored-procedures-transact-sql.md)   
 [Katalogsichten des Abfragespeichers &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/query-store-catalog-views-transact-sql.md)  
  
  