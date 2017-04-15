---
title: "Angeben der Verarbeitungsreihenfolge von Mergeartikeln | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Artikel [SQL Server-Replikation], Verarbeitungsreihenfolge"
  - "Mergereplikation [SQL Server-Replikation], Verarbeitungsreihenfolge von Artikeln"
ms.assetid: d151e2c5-cf50-4cb3-a829-8f32455dbd66
caps.latest.revision: 34
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 34
---
# Angeben der Verarbeitungsreihenfolge von Mergeartikeln
  Ab [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]haben Sie die Möglichkeit, die Standardreihenfolge zu überschreiben, in der Artikel bei Mergeveröffentlichungen verarbeitet werden. Die Änderung der Standardverarbeitungsreihenfolge ist z. B. dann sinnvoll, wenn Sie für die Definition von referenzieller Integrität Trigger verwenden und diese Trigger in einer bestimmten Reihenfolge ausgelöst werden sollen.  
  
 **So geben Sie die Verarbeitungsreihenfolge von Artikeln an**  
  
-   Replikationsprogrammierung mit Transact-SQL: [Geben Sie die Verarbeitung Reihenfolge von Merge Tabellenartikel & #40; Replikationsprogrammierung mit Transact-SQL & #41;](../../../relational-databases/replication/publish/specify the processing order of merge table articles.md)  
  
## Funktionsweise bei der Festlegung der Verarbeitungsreihenfolge  
 Während der Mergesynchronisierung werden die Artikel standardmäßig entsprechend den Abhängigkeiten zwischen den Objekten geordnet. Zu diesen Abhängigkeiten gehören auch die in den Basistabellen definierten DRI-Einschränkungen (Deklarative referenzielle Integrität). Bei der Verarbeitung werden die Änderungen in einer Tabelle aufgezählt und dann angewendet. Wenn es keine deklarative referenzielle Integrität gibt, zwischen den Tabellenartikeln aber Joinfilter oder logische Datensätze vorhanden sind, werden die Artikel entsprechend der in den Filtern und logischen Datensätzen festgelegten Reihenfolge verarbeitet. Artikel nicht im Zusammenhang mit per DRI, joinfiltern, logischen Datensätzen oder andere Abhängigkeiten werden anhand Ihres Artikels in verarbeitet die [Sysmergearticles & #40; Transact-SQL & #41;](../../../relational-databases/system-tables/sysmergearticles-transact-sql.md) Systemtabelle.  
  
 Angenommen, es gibt eine Veröffentlichung mit der **SalesOrderHeader** - und der **SalesOrderDetail** -Tabelle mit einer **SalesOrderID** -Primärschlüsselspalte in der **SalesOrderHeader** -Tabelle und einer zugehörigen **SalesOrderID** -Fremdschlüsselspalte in der **SalesOrderDetail** -Tabelle. Bei der Synchronisierung verhindert die Mergereplikation Fremdschlüsselverletzungen, indem alle neuen Zeilen zuerst in **SalesOrderHeader** und erst dann die entsprechenden Zeilen in **SalesOrderDetail**eingefügt werden. Genauso werden erst Zeilen aus der **SalesOrderDetail** -Tabelle gelöscht, bevor die entsprechenden Zeilen auch aus der **SalesOrderHeader**-Tabelle gelöscht werden.  
  
 In einigen Anwendungen wird die referenzielle Integrität durch Datenbanktrigger oder auf Anwendungsebene und nicht per DRI erzwungen. So könnte z. B. die oben beschriebene Veröffentlichung statt DRI in der **SalesOrderDetail** -Tabelle einen INSERT-Trigger besitzen, der sicherstellt, dass die zugehörige Zeile in der **SalesOrderHeader** -Tabelle vorhanden ist, bevor eine Einfügung zugelassen wird. Die**SalesOrderHeader** -Tabelle könnte einen DELETE-Trigger enthalten, der sicherstellt, dass in **SalesOrderDetail** keine zugehörigen Zeilen vorhanden sind, bevor eine Löschung zugelassen wird. Bei der Mergereplikation werden zur Bestimmung der Verarbeitungsreihenfolge der Artikel keine Trigger berücksichtigt, da dieser Replikationstyp das Ergebnis des Triggers nicht vorhersehen kann. Darüber hinaus kann diese Replikation auch keine auf Anwendungsebene definierten Einschränkungen berücksichtigen.  
  
 Wenn die referenzielle Integrität durch Trigger oder auf Anwendungsebene gewahrt wird, müssen Sie die Reihenfolge angeben, in der die Artikel verarbeitet werden sollen. Im Beispiel mit den Triggern würden Sie dann angeben, dass die **SalesOrderHeader** -Tabelle vor der **SalesOrderDetail**-Tabelle zu verarbeiten ist, weil die Artikelreihenfolge auf der Einfügereihenfolge basiert. Bei der Mergereplikation wird die Reihenfolge der Löschungen automatisch umgekehrt. Das Nichtfestlegen einer Artikelverarbeitungsreihenfolge führt nicht zu einem Scheitern der Mergereplikation, weil der Merge-Agent mit der Verarbeitung der Artikel fortfährt, wenn es zu einer Einschränkungsverletzung kommt. Wenn die anderen Artikel verarbeitet sind, versucht der Agent, alle Operationen, die fehlgeschlagen sind, erneut auszuführen. Durch das Angeben einer Artikelverarbeitungsreihenfolge werden lediglich solche Neuversuche und die damit verbundene zusätzliche Verarbeitung verhindert. Wenn Sie eine falsche Reihenfolge angeben (z. B. eine, bei der die Detaildatensätze vor den Headerdatensätzen verarbeitet werden), versucht die Mergereplikation die Verarbeitung so lange, bis sie gelingt.  
  
## Siehe auch  
 [Artikeloptionen für die Mergereplikation](../../../relational-databases/replication/merge/article-options-for-merge-replication.md)   
 [Gruppieren von Änderungen an verknüpften Zeilen mithilfe von logischen Datensätzen](../../../relational-databases/replication/merge/group-changes-to-related-rows-with-logical-records.md)   
 [Joinfilter](../../../relational-databases/replication/merge/join-filters.md)  
  
  