---
title: "Wiederherstellen eines Datenbank-Hauptschlüssels | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
caps.latest.revision: 16
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: c2833a4b91d4465e126c0a393e756ab09106d1c8
ms.contentlocale: de-de
ms.lasthandoff: 06/22/2017

---
# <a name="restore-a-database-master-key"></a>Wiederherstellen eines Datenbank-Hauptschlüssels
  In diesem Thema wird beschrieben, wie der Datenbank-Hauptschlüssel in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[tsql](../../../includes/tsql-md.md)]wiederhergestellt wird.  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Sicherheit](#Security)  
  
-   [So stellen Sie den Datenbank-Hauptschlüssel mithilfe von Transact-SQL wieder her](#SSMSProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Bei der Wiederherstellung des Hauptschlüssels werden alle Schlüssel von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] entschlüsselt, die mit dem aktuell aktiven Hauptschlüssel verschlüsselt sind. Diese Schlüssel werden dann mit dem wiederhergestellten Hauptschlüssel verschlüsselt. Die Ausführung dieses ressourcenintensiven Vorgangs sollte außerhalb der Hauptzeiten geplant werden. Falls der aktuelle Datenbank-Hauptschlüssel nicht geöffnet ist oder nicht geöffnet werden kann oder falls einer der Schlüssel, die mit ihm verschlüsselt sind, nicht entschlüsselt werden kann, kann der Wiederherstellungsvorgang nicht erfolgreich ausgeführt werden.  
  
-   Falls einer dieser Entschlüsselungsvorgänge nicht erfolgreich ausgeführt werden kann, tritt bei der Wiederherstellung ein Fehler auf. Sie können die FORCE-Option verwenden, um Fehler zu ignorieren, dies kann jedoch zum Verlust von Daten führen, die nicht entschlüsselt werden können.  
  
-   Wurde der Hauptschlüssel mit dem Diensthauptschlüssel verschlüsselt, wird auch der wiederhergestellte Hauptschlüssel mit dem Diensthauptschlüssel verschlüsselt.  
  
-   Falls in der aktuellen Datenbank kein Hauptschlüssel vorhanden ist, wird von RESTORE MASTER KEY ein Hauptschlüssel erstellt. Der neue Hauptschlüssel wird nicht automatisch mit dem Diensthauptschlüssel verschlüsselt.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert die CONTROL-Berechtigung für die Datenbank.  
  
##  <a name="SSMSProcedure"></a> Verwenden von SQL Server Management Studio mit Transact-SQL  
  
#### <a name="to-restore-the-database-master-key"></a>So stellen Sie den Datenbank-Hauptschlüssel wieder her  
  
1.  Rufen Sie entweder von einem physischen Sicherungsmedium oder einem Verzeichnis im lokalen Dateisystem eine Kopie des gesicherten Datenbank-Hauptschlüssels ab.  
  
2.  Stellen Sie im Objekt-Explorer **** eine Verbindung mit einer [!INCLUDE[ssDE](../../../includes/ssde-md.md)]-Instanz her.  
  
3.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
4.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  Der Dateipfad zum Schlüssel und das Kennwort (sofern es vorhanden ist) des Schlüssels unterscheiden sich von den obigen Informationen. Stellen Sie sicher, dass beide für den Server und die Schlüsseleinrichtung spezifisch sind.  
  
 Weitere Informationen finden Sie unter [RESTORE MASTER KEY &#40;Transact-SQL&#41;](../../../t-sql/statements/restore-master-key-transact-sql.md).  
  
  