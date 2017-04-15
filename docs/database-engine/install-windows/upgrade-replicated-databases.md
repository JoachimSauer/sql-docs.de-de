---
title: "Aktualisieren von replizierten Datenbanken | Microsoft Docs"
ms.custom: ""
ms.date: "02/16/2016"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "setup-install"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Upgrades für Mergereplikationsdatenbanken [SQL Server-Replikation]"
  - "Replikation [SQL Server], Ausführen von Upgrades"
  - "Transaktionsreplikation, Datenbankupgrades"
  - "Momentaufnahmereplikation [SQL Server], Datenbankupgrades"
  - "Aktualisieren von replizierten Datenbanken"
ms.assetid: 9926a4f7-bcd8-4b9b-9dcf-5426a5857116
caps.latest.revision: 74
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 73
---
# Aktualisieren von replizierten Datenbanken
  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] unterstützt das Aktualisieren replizierter Datenbanken von früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Während der Aktualisierung eines Knotens müssen die auf anderen Knoten ausgeführten Aktivitäten nicht beendet werden. Stellen Sie sicher, dass die Regeln, die im Hinblick auf die in einer Topologie unterstützten Versionen gelten, eingehalten werden:  
  
-   Für den Verteiler ist jede Version zulässig, die der Verleger-Version entspricht oder höher als diese ist. (In vielen Fällen gehören Verteiler und Verleger derselben Instanz an.)  
  
-   Für den Verleger ist jede Version zulässig, die der Verteiler-Version entspricht oder niedriger als diese ist.  
  
-   Die Abonnenten-Version ist vom Veröffentlichungstyp abhängig:  
  
    -   Ein Abonnent einer Transaktionsveröffentlichung kann einer der beiden Versionen im Rahmen der Verlegerversion angehören. Beispiel: Ein [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] -Verleger kann mit [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] - und [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] -Abonnenten verwendet werden; und ein [!INCLUDE[ssSQL15](../../includes/sssql15-md.md)] -Verleger kann mit [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] - und  [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] -Abonnenten verwendet werden.  
  
    -   Für einen Abonnenten einer Mergeveröffentlichung ist jede Version zulässig, die der Verleger-Version entspricht oder niedriger als diese ist.  
  
> [!NOTE]  
>  Das Thema ist sowohl in der Hilfe zum Setup als auch in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation enthalten. Über die fett formatierten Links in der Hilfe zum Setup gelangen Sie zu Themen, die nur in der Onlinedokumentation verfügbar sind.  
  
## Führen Sie den Protokolllese-Agent für die Transaktionsreplikation vor dem Upgrade aus.  
 Bevor Sie auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]aktualisieren, müssen Sie sich vergewissern, dass alle Transaktionen mit ausgeführtem Commit von veröffentlichten Tabellen vom Protokolllese-Agent verarbeitet wurden. Um sicherzustellen, dass alle Transaktionen verarbeitet wurden, führen Sie die folgenden Schritte für jede Datenbank aus, die Transaktionsveröffentlichungen enthält:  
  
1.  Stellen Sie sicher, dass der Protokolllese-Agent für die Datenbank ausgeführt wird. Standardmäßig wird der Agent ununterbrochen ausgeführt.  
  
2.  Beenden Sie die Benutzeraktivität auf veröffentlichten Tabellen.  
  
3.  Warten Sie eine gewissen Zeit, bis der Protokolllese-Agent die Transaktionen in die Verteilungsdatenbank kopiert hat, und beenden Sie dann den Agent.  
  
4.  Führen Sie [sp_replcmds](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md) aus, um zu überprüfen, ob alle Transaktionen verarbeitet wurden. Das Resultset dieser Prozedur sollte leer sein.  
  
5.  Führen Sie [sp_replflush](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md) aus, um die Verbindung von „sp_replcmds“ zu trennen.  
  
6.  Führen Sie das Serverupgrade auf [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] aus.  
  
7.  Starten Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent und den Protokolllese-Agent neu, wenn sie nach dem Upgrade nicht automatisch starten.  
  
## Ausführen von Agents nach dem Upgrade für die Mergereplikation  
 Führen Sie nach dem Upgrade für jede Mergeveröffentlichung den Momentaufnahme-Agent und für jedes Abonnement den Merge-Agent aus, um die Replikationsmetadaten zu aktualisieren. Sie müssen die neue Momentaufnahme nicht anwenden, da sie für die erneute Initialisierung der Abonnements nicht benötigt wird. Die Metadaten des Abonnements werden aktualisiert, sobald der Merge-Agent zum ersten Mal nach dem Upgrade ausgeführt wird. Dies bedeutet, dass die Abonnementdatenbank während des Upgrades des Verlegers online und aktiv bleiben kann.  
  
 Die Mergereplikation speichert die Metadaten der Veröffentlichung und des Abonnements in einer Reihe von Systemtabellen in den Veröffentlichungs- und Abonnement-Datenbanken. Bei Ausführung des s werden die Veröffentlichungsmetadaten aktualisiert, und bei Ausführung des Merge-Agents werden die Abonnementmetadaten aktualisiert. Der Agent wird nur benötigt, um eine Momentaufnahme der Veröffentlichung zu generieren. Wenn bei einer Mergeveröffentlichung parametrisierte Filter verwendet werden, gibt es auch für jede Partition eine Momentaufnahme. Diese partitionierten Momentaufnahmen zu aktualisieren, ist nicht erforderlich.  
  
 Die Agents werden in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], im Replikationsmonitor oder in der Befehlszeile ausgeführt. Weitere Informationen zum Ausführen des Momentaufnahme-Agents finden Sie unter den folgenden Themen:  
  
-   [Erstellen und Anwenden der Anfangsmomentaufnahme](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [Starten und Beenden eines Replikations-Agents &#40;SQL Server Management Studio&#41;](../../relational-databases/replication/agents/start-and-stop-a-replication-agent-sql-server-management-studio.md)  
  
-   [Erstellen und Anwenden der Anfangsmomentaufnahme](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)  
  
-   [Ausführbare Konzepte für die Programmierung von Replikations-Agents](../../relational-databases/replication/concepts/replication-agent-executables-concepts.md)  
  
 Weitere Informationen zum Ausführen des Merge-Agents finden Sie unter den folgenden Themen:  
  
-   [Synchronisieren eines Pullabonnements](../../relational-databases/replication/synchronize-a-pull-subscription.md)  
  
-   [Synchronisieren eines Pushabonnements](../../relational-databases/replication/synchronize-a-push-subscription.md)  
  
 Nach dem Upgrade von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in einer Topologie, in der die Mergereplikation verwendet wird, müssen Sie den Kompatibilitätsgrad aller Veröffentlichungen ändern, um neue Funktionen verwenden zu können.  
  
## Aktualisieren auf die Standard Edition, Workgroup Edition oder Express Edition  
 Bevor eine Edition von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] auf eine andere Edition aktualisiert wird, sollten Sie überprüfen, ob die derzeit verwendete Funktionalität in der Edition, die Ziel des Upgrades ist, unterstützt wird. Weitere Informationen finden Sie im Abschnitt zur Replikation im Thema [Von den SQL Server 2016-Editionen unterstützte Funktionen](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md).  
  
## Websynchronisierung für die Mergereplikation  
 Bei der Websynchronisierung für die Mergereplikation ist es erforderlich, dass die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Replikationsüberwachung (replisapi.dll) in das virtuelle Verzeichnis auf dem Server mit Internetinformationsdienste (Internet Information Services, IIS) kopiert wird, der für die Synchronisierung verwendet wird. Wenn Sie die Websynchronisierung konfigurieren, wird die Datei vom Assistenten zum Konfigurieren der Websynchronisierung in das virtuelle Verzeichnis kopiert. Wenn Sie die auf dem IIS-Server installierten [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Komponenten aktualisieren, müssen Sie replisapi.dll manuell vom Verzeichnis COM in das virtuelle Verzeichnis auf dem IIS-Server kopieren. Weitere Informationen zur Konfiguration der Websynchronisierung finden Sie unter [Konfigurieren der Websynchronisierung](../../relational-databases/replication/configure-web-synchronization.md).  
  
## Wiederherstellen einer replizierten Datenbank von einer früheren Version  
 Um sicherzustellen, dass die Replikationseinstellungen beibehalten werden, wenn die Sicherung einer replizierten Datenbank mithilfe einer früheren Version wiederhergestellt wird, stellen Sie die Sicherung auf einem Server und in einer Datenbank wieder her, deren Namen mit den Namen des Servers und der Datenbank übereinstimmen, von dem bzw. der die Sicherung erstellt wurde.  
  
## Siehe auch  
 [Verwaltung &#40;Replikation&#41;](../../relational-databases/replication/administration/administration-replication.md)   
 [Abwärtskompatibilität von Replikationen](../../relational-databases/replication/replication-backward-compatibility.md)   
 [Neuigkeiten &#40;Replikation&#41;](../../relational-databases/replication/what-s-new-replication.md)   
 [Unterstützte Versions- und Editionsupgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)   
 [Aktualisieren auf SQL Server 2016](../../database-engine/install-windows/upgrade-to-sql-server-2016.md)  
  
  