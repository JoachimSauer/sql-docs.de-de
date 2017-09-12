---
title: "Beispiel: Offlinewiederherstellung der primären Dateigruppe und einer weiteren Dateigruppe (vollständiges Wiederherstellungsmodell) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-backup-restore
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- offline restores [SQL Server]
- restore sequences [SQL Server], offline
ms.assetid: 7d6c50eb-dc84-4d66-855a-0b5f1bd89737
caps.latest.revision: 32
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: a89ca3ffb79c4ca4001356f0963f7fffdefd954f
ms.contentlocale: de-de
ms.lasthandoff: 06/22/2017

---
# <a name="example-offline-restore-of-primary-and-one-other-filegroup-full-recovery-model"></a>Beispiel: Offlinewiederherstellung der primären Dateigruppe und einer weiteren Dateigruppe (vollständiges Wiederherstellungsmodell)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-xxxx-xxxx-xxx-md.md)]

  Dieses Thema ist nur für Datenbanken relevant, in denen mehrere Dateigruppen enthalten sind und für die das vollständige Wiederherstellungsmodell verwendet wird.  
  
 In diesem Beispiel sind in der Datenbank `adb` drei Dateigruppen enthalten. Die Dateigruppen `A` und `C` weisen Lese-/Schreibzugriff auf, und die Dateigruppe `B` ist schreibgeschützt. Die primäre Dateigruppe und die Dateigruppe `B` sind beschädigt, die Dateigruppen `A` und `C` sind jedoch intakt. Vor dem Notfall waren alle Dateigruppen online.  
  
 Der Datenbankadministrator entscheidet sich, die primäre Dateigruppe und Dateigruppe `B`wiederherzustellen. Für die Datenbank wird das vollständige Wiederherstellungsmodell verwendet, weshalb vor dem Beginn der Wiederherstellung eine Protokollfragmentsicherung der Datenbank erstellt werden muss. Wenn die Datenbank online geschaltet wird, werden die Dateigruppen `A` und `C` automatisch online geschaltet.  
  
> [!NOTE]  
>  Die Offlinewiederherstellungssequenz verfügt über weniger Schritte als die Onlinewiederherstellung einer schreibgeschützten Datei. Ein Beispiel finden Sie unter [Beispiel: Onlinewiederherstellung einer schreibgeschützten Datei &#40;vollständiges Wiederherstellungsmodell&#41;](../../relational-databases/backup-restore/example-online-restore-of-a-read-only-file-full-recovery-model.md) Die gesamte Datenbank ist jedoch für die Dauer der Wiederherstellungssequenz offline.  
  
## <a name="tail-log-backup"></a>Sicherung des Protokollfragments  
 Vor dem Wiederherstellen der Datenbank muss der Datenbankadministrator das Protokollfragment sichern. Weil die Datenbank beschädigt ist, muss zum Erstellen der Sicherung des Protokollfragments die NO_TRUNCATE-Option verwendet werden:  
  
```  
BACKUP LOG adb TO tailLogBackup   
   WITH NORECOVERY, NO_TRUNCATE  
```  
  
 Bei der Sicherung des Protokollfragments handelt es sich um die letzte Sicherung im Rahmen der folgenden Wiederherstellungssequenzen.  
  
## <a name="restore-sequence"></a>Wiederherstellungssequenz  
 Zum Wiederherstellen der primären Dateigruppe und der Dateigruppe `B`verwendet der Datenbankadministrator die Wiederherstellungssequenz ohne die Option PARTIAL folgendermaßen:  
  
```  
RESTORE DATABASE adb FILEGROUP='Primary' FROM backup1   
WITH NORECOVERY  
RESTORE DATABASE adb FILEGROUP='B' FROM backup2   
WITH NORECOVERY  
RESTORE LOG adb FROM backup3 WITH NORECOVERY  
RESTORE LOG adb FROM backup4 WITH NORECOVERY  
RESTORE LOG adb FROM backup5 WITH NORECOVERY  
RESTORE LOG adb FROM tailLogBackup WITH RECOVERY  
```  
  
 Die nicht wiederhergestellten Dateien werden automatisch online geschaltet. Alle Dateigruppen sind jetzt online.  
  
## <a name="see-also"></a>Siehe auch  
 [Onlinewiederherstellungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/online-restore-sql-server.md)   
 [Schrittweise Wiederherstellungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/piecemeal-restores-sql-server.md)   
 [Dateiwiederherstellungen &#40;vollständiges Wiederherstellungsmodell&#41;](../../relational-databases/backup-restore/file-restores-full-recovery-model.md)   
 [Anwenden von Transaktionsprotokollsicherungen &#40;SQL Server&#41;](../../relational-databases/backup-restore/apply-transaction-log-backups-sql-server.md)   
 [RESTORE &#40;Transact-SQL&#41;](../../t-sql/statements/restore-statements-transact-sql.md)  
  
  