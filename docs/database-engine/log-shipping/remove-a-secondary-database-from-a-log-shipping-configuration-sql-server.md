---
title: "Entfernen einer sekund&#228;ren Datenbank aus einer Protokollversandkonfiguration (SQL Server) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-high-availability"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Löschen von sekundären Datenbanken"
  - "Sekundäre Datenbanken [SQL Server], beim Protokollversand"
  - "Entfernen von sekundären Datenbanken"
  - "Sekundäre Datendateien [SQL Server], entfernen"
  - "Protokollversand [SQL Server], sekundäre Datenbanken"
ms.assetid: ebe368a4-ca1c-45d0-9a71-3ddbd5b26a8e
caps.latest.revision: 19
author: "MikeRayMSFT"
ms.author: "mikeray"
manager: "jhubbard"
caps.handback.revision: 19
---
# Entfernen einer sekund&#228;ren Datenbank aus einer Protokollversandkonfiguration (SQL Server)
  In diesem Thema wird beschrieben, wie eine sekundäre Datenbank für den Protokollversand in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]entfernt wird.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Sicherheit](#Security)  
  
-   **So entfernen Sie eine sekundäre Datenbank für den Protokollversand mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
-   [Verwandte Aufgaben](#RelatedTasks)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Die gespeicherten Prozeduren für den Protokollversand erfordern die Mitgliedschaft in der festen Serverrolle **sysadmin**.  
  
##  <a name="SSMSProcedure"></a> Verwendung von SQL Server Management Studio  
  
#### So entfernen Sie eine sekundäre Datenbank für den Protokollversand  
  
1.  Stellen Sie eine Verbindung mit der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] her, die derzeit als primärer Server für den Protokollversand verwendet wird, und erweitern Sie diese Instanz.  
  
2.  Erweitern Sie **Datenbanken**, klicken Sie mit der rechten Maustaste auf die primäre Datenbank für den Protokollversand, und klicken Sie dann auf **Eigenschaften**.  
  
3.  Klicken Sie unter **Seite auswählen**auf **Transaktionsprotokollversand**.  
  
4.  Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken**auf die Datenbank, die Sie entfernen wollen.  
  
5.  Klicken Sie auf **Entfernen**.  
  
6.  Klicken Sie auf **OK** , um die Konfiguration zu aktualisieren.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
#### So entfernen Sie eine sekundäre Datenbank  
  
1.  Führen Sie auf dem primären Server [sp_delete_log_shipping_primary_secondary](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-primary-secondary-transact-sql.md) aus, um die Informationen zur sekundären Datenbank vom primären Server zu löschen.  
  
2.  Führen Sie auf dem sekundären Server [sp_delete_log_shipping_secondary_database](../../relational-databases/system-stored-procedures/sp-delete-log-shipping-secondary-database-transact-sql.md) aus, um die sekundäre Datenbank zu löschen.  
  
    > [!NOTE]  
    >  Falls keine anderen sekundären Datenbanken mit der gleichen sekundären ID vorhanden sind, wird **sp_delete_log_shipping_secondary_primary** von **sp_delete_log_shipping_secondary_database** aufgerufen und löscht den Eintrag für die sekundäre ID sowie die Kopier- und Wiederherstellungsaufträge.  
  
3.  Deaktivieren Sie auf dem sekundären Server den Kopier- und Wiederherstellungsauftrag. Weitere Informationen finden sie unter [Disable or Enable a Job](../../ssms/agent/disable-or-enable-a-job.md).  
  
##  <a name="RelatedTasks"></a> Verwandte Aufgaben  
  
-   [Aktualisieren des Protokollversands auf SQL Server 2016 &#40;Transact-SQL&#41;](../../database-engine/log-shipping/upgrading-log-shipping-to-sql-server-2016-transact-sql.md)  
  
-   [Konfigurieren des Protokollversands &#40;SQL Server&#41;](../../database-engine/log-shipping/configure-log-shipping-sql-server.md)  
  
-   [Hinzufügen einer sekundären Datenbank zu einer Protokollversandkonfiguration &#40;SQL Server&#41;](../../database-engine/log-shipping/add-a-secondary-database-to-a-log-shipping-configuration-sql-server.md)  
  
-   [Entfernen des Protokollversands &#40;SQL Server&#41;](../../database-engine/log-shipping/remove-log-shipping-sql-server.md)  
  
-   [Anzeigen des Protokollversandberichts &#40;SQL Server Management Studio&#41;](../../database-engine/log-shipping/view-the-log-shipping-report-sql-server-management-studio.md)  
  
-   [Überwachen des Protokollversands &#40;Transact-SQL&#41;](../../database-engine/log-shipping/monitor-log-shipping-transact-sql.md)  
  
-   [Failover zu einer sekundären Datenbank für den Protokollversand &#40;SQL Server&#41;](../../database-engine/log-shipping/fail-over-to-a-log-shipping-secondary-sql-server.md)  
  
## Siehe auch  
 [Informationen zum Protokollversand &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Protokollversandtabellen und gespeicherte Prozeduren](../../database-engine/log-shipping/log-shipping-tables-and-stored-procedures.md)  
  
  