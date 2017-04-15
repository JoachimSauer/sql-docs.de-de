---
title: "Verschieben eines UCPs von einer SQL Server-Instanz in eine andere (SQL Server-Hilfsprogramm) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b402fd9e-0bea-4c38-a371-6ed7fea12e96
caps.latest.revision: 9
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 9
---
# Verschieben eines UCPs von einer SQL Server-Instanz in eine andere (SQL Server-Hilfsprogramm)
  In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] einen Steuerungspunkt für das Hilfsprogramm (UCP) von einer Instanz von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in eine andere verschieben.  
  
##  <a name="SSMSProcedure"></a> Verwendung von SQL Server Management Studio  
  
#### Verschieben Sie einen UCP von einer SQL Server-Instanz in eine andere.  
  
1.  Erstellen Sie einen neuen UCP für die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die die neue Hostinstanz des UCPs darstellt. Weitere Informationen finden Sie unter [Erstellen eines Steuerungspunkts für das SQL Server-Hilfsprogramm &#40;SQL Server-Hilfsprogramm&#41;](../../relational-databases/manage/create-a-sql-server-utility-control-point-sql-server-utility.md).  
  
2.  Wenn nicht standardmäßige Richtlinieneinstellungen für beliebige Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Hilfsprogramm festgelegt wurden, notieren Sie sich die Richtlinienschwellenwerte, damit Sie sie auf dem neuen UCP entsprechend festlegen können. Standardrichtlinien werden angewendet, sobald dem neuen UCP Instanzen hinzugefügt werden. Wenn Standardrichtlinien gültig sind, wird in der Listenansicht des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms in der Spalte **Richtlinientyp** der Wert **Global** angezeigt.  
  
3.  Entfernen Sie alle verwalteten Instanzen aus dem alten UCP. Weitere Informationen finden Sie unter [Entfernen einer Instanz von SQL Server aus dem SQL Server-Hilfsprogramm](../../relational-databases/manage/remove-an-instance-of-sql-server-from-the-sql-server-utility.md).  
  
4.  Sichern Sie das Utility Management Data Warehouse (UMDW) vom alten UCP aus. Der Dateiname ist Sysutility_mdw_\<GUID>_DATA. Der Standardspeicherort der Datenbank ist \<Systemlaufwerk>:\Programme\Microsoft SQL Server\MSSQL10_50.<UCP_Name>\MSSQL\Data\\, wobei \<Systemlaufwerk> normalerweise dem Laufwerk C:\ entspricht. Weitere Informationen finden Sie unter [Kopieren von Datenbanken durch Sichern und Wiederherstellen](../../relational-databases/databases/copy-databases-with-backup-and-restore.md).  
  
5.  Stellen Sie die Sicherung des UMDWs auf dem neuen UCP wieder her. Weitere Informationen finden Sie unter [Kopieren von Datenbanken durch Sichern und Wiederherstellen](../../relational-databases/databases/copy-databases-with-backup-and-restore.md).  
  
6.  Registrieren Sie Instanzen im neuen UCP, um sie als verwaltete Instanzen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Hilfsprogramms einzurichten. Weitere Informationen finden Sie unter [ Registrieren einer Instanz von SQL Server &#40;SQL Server-Hilfsprogramm&#41;](../../relational-databases/manage/enroll-an-instance-of-sql-server-sql-server-utility.md).  
  
7.  Implementieren Sie ggf. benutzerdefinierte Richtliniendefinitionen für die verwalteten Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
8.  Warten Sie ungefähr eine Stunde, bis Datensammlungs- und Aggregationsvorgänge abgeschlossen sind.  
  
9. Um Daten zu aktualisieren, klicken Sie mit der rechten Maustaste auf den Knoten **Verwaltete Instanzen** im **Hilfsprogramm-Explorer**, und wählen Sie dann **Aktualisieren** aus. Listenansichtsdaten werden im Inhaltsbereich von **Hilfsprogramm-Explorer** angezeigt. Weitere Informationen finden Sie unter [Anzeigen der Ergebnisse zu Ressourcenintegritätsrichtlinien &#40;SQL Server-Hilfsprogramm&#41;](../../relational-databases/manage/view-resource-health-policy-results-sql-server-utility.md).  
  
## Siehe auch  
 [Funktionen und Tasks im SQL Server-Hilfsprogramm](../../relational-databases/manage/sql-server-utility-features-and-tasks.md)   
 [Registrieren einer Instanz von SQL Server &#40;SQL Server-Hilfsprogramm&#41;](../../relational-databases/manage/enroll-an-instance-of-sql-server-sql-server-utility.md)  
  
  