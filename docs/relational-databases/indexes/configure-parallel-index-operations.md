---
title: "Konfigurieren von Parallelindexvorg&#228;ngen | Microsoft Docs"
ms.custom: ""
ms.date: "02/17/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-indexes"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Index (parallele Vorgänge) [SQL Server]"
  - "Prozessoren [SQL Server], parallele Indexvorgänge"
  - "Max. Grad an Parallelität (Option)"
  - "MAXDOP-Indexoption, parallele Indexvorgänge"
  - "Parallele Indexvorgänge [SQL Server]"
ms.assetid: 8ec8c71e-5fc1-443a-92da-136ee3fc7f88
caps.latest.revision: 43
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 42
---
# Konfigurieren von Parallelindexvorg&#228;ngen
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  In diesem Thema wird der maximale Grad an Parallelität beschrieben und erläutert, wie Sie diese Einstellung in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern. Auf Multiprozessorcomputern, auf denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise oder höher ausgeführt wird, werden für Indexanweisungen möglicherweise mehrere Prozessoren verwendet, um die mit der Indexanweisung verknüpften Scan-, Sortierungs- und Indexvorgänge auszuführen. Dies geschieht in gleicher Weise wie bei anderen Abfragen. Die Anzahl der Prozessoren, die zur Ausführung einer einzelnen Indexanweisung verwendet werden, wird durch die Konfigurationsoption [Max. Grad an Parallelität](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md) sowie durch die aktuelle Arbeitslast und die Indexstatistiken bestimmt. Mit der Option Max. Grad an Parallelität wird die maximale Anzahl der Prozessoren festgelegt, die bei der Ausführung paralleler Pläne verwendet werden sollen. Wenn [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] feststellt, dass das System ausgelastet ist, wird der Grad der Parallelität des Indexvorgangs automatisch verringert, bevor mit dem Ausführen der Anweisung begonnen wird. [!INCLUDE[ssDE](../../includes/ssde-md.md)] kann den Grad der Parallelität auch verringern, wenn die führende Schlüsselspalte eines nicht partitionierten Indexes eine begrenzte Anzahl unterschiedlicher Werte aufweist, oder wenn die Häufigkeit der einzelnen unterschiedlichen Werte stark schwankt.  
  
> [!NOTE]  
>  Parallele Indexvorgänge sind nicht in jeder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Edition verfügbar. Weitere Informationen finden Sie unter [Von den SQL Server 2016-Editionen unterstützte Funktionen](../Topic/Features%20Supported%20by%20the%20Editions%20of%20SQL%20Server%202016.md).  
  
 **In diesem Thema**  
  
-   **Vorbereitungen:**  
  
     [Einschränkungen](#Restrictions)  
  
     [Sicherheit](#Security)  
  
-   **Festlegen des maximalen Grads an Parallelität mit:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Restrictions"></a> Einschränkungen  
  
-   Mit der Anzahl der Prozessoren, die vom Abfrageoptimierer verwendet wird, kann zumeist eine optimale Leistung gewährleistet werden. Allerdings können bestimmte Vorgänge, wie das Erstellen, erneute Erstellen oder Löschen sehr großer Indizes die Ressourcen stark beanspruchen, wodurch während des Indexvorgangs möglicherweise nicht genügend Ressourcen für andere Anwendungen und Datenbankvorgänge verfügbar sind. Wenn dieses Problem auftritt, können Sie die zum Ausführen der Indexanweisung verwendete maximale Anzahl von Prozessoren manuell konfigurieren, indem Sie die Anzahl von Prozessoren für den Indexvorgang verringern.  
  
-   Die MAXDOP-Indexoption überschreibt die Max. Grad an Parallelität-Konfigurationsoption, jedoch nur für die Abfrage, die diese Option angibt. In der folgenden Tabelle werden die gültigen ganzzahligen Werte aufgelistet, die mit der Max. Grad an Parallelität-Konfigurationsoption und der MAXDOP-Indexoption angegeben werden können.  
  
    |Wert|Beschreibung|  
    |-----------|-----------------|  
    |0|Gibt an, dass der Server die Anzahl der CPUs festlegt, die verwendet werden, abhängig von der aktuellen Systemarbeitsauslastung. Dies ist die Standardeinstellung und die empfohlene Einstellung.|  
    |1|Unterdrückt das Generieren paralleler Pläne. Die Operationen werden dann nacheinander, also seriell ausgeführt.|  
    |2-64|Schränkt die Anzahl der Prozessoren auf den angegebenen Wert ein. In Abhängigkeit von der aktuellen Systemlast kann eine geringere Anzahl von Prozessoren verwendet werden. Wird ein Wert angegeben, der über der Anzahl der verfügbaren CPUs liegt, wird die tatsächliche Anzahl der CPUs verwendet.|  
  
-   Die parallele Indexausführung und die MAXDOP-Indexoption gelten für die folgenden [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen:  
  
    -   CREATE INDEX  
  
    -   ALTER INDEX REBUILD  
  
    -   DROP INDEX (Gilt nur für gruppierte Indizes.)  
  
    -   ALTER TABLE ADD (Index) CONSTRAINT  
  
    -   ALTER TABLE DROP (gruppierter Index) CONSTRAINT  
  
-   In der ALTER INDEX REORGANIZE-Anweisung kann die MAXDOP-Indexoption nicht angegeben werden.  
  
-   Die Speicheranforderungen für partitionierte Indexvorgänge, bei denen Sortiervorgänge erforderlich sind, können größer sein, wenn der Abfrageoptimierer Grade der Parallelität beim Erstellungsvorgang verwendet. Je höher der Grad der Parallelität ist, desto höher ist der Speicherbedarf. Weitere Informationen finden Sie unter [Partitioned Tables and Indexes](../../relational-databases/partitions/partitioned-tables-and-indexes.md).  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Erfordert die ALTER-Berechtigung in der Tabelle oder Sicht.  
  
##  <a name="SSMSProcedure"></a> Verwendung von SQL Server Management Studio  
  
#### So legen Sie den maximalen Grad an Parallelität für einen Index fest  
  
1.  Klicken Sie im Objekt-Explorer auf das Pluszeichen, um die Datenbank mit der Tabelle zu erweitern, in der Sie den maximalen Grad an Parallelität für einen Index festlegen möchten.  
  
2.  Erweitern Sie den Ordner **Tabellen** .  
  
3.  Klicken Sie auf das Pluszeichen, um die Tabelle zu erweitern, in der Sie den maximalen Grad an Parallelität für einen Index festlegen möchten.  
  
4.  Erweitern Sie den Ordner **Indizes** .  
  
5.  Klicken Sie mit der rechten Maustaste auf den Index, für den Sie den maximalen Grad an Parallelität festlegen möchten, und wählen Sie **Eigenschaften** aus.  
  
6.  Wählen Sie unter **Seite auswählen**die Option **Optionen**aus.  
  
7.  Wählen Sie **Maximaler Grad an Parallelität**aus, und geben Sie dann einen Wert zwischen 1 und 64 ein.  
  
8.  Klicken Sie auf **OK**.  
  
##  <a name="TsqlProcedure"></a> Verwenden von Transact-SQL  
  
#### So legen Sie den maximalen Grad an Parallelität für einen vorhandenen Index fest  
  
1.  Stellen Sie im Objekt-Explorer ** **eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    USE AdventureWorks2012;   
    GO  
    /*Alters the IX_ProductVendor_VendorID index on the Purchasing.ProductVendor table so that, if the server has eight or more processors, the Database Engine will limit the execution of the index operation to eight or fewer processors.  
    */  
    ALTER INDEX IX_ProductVendor_VendorID ON Purchasing.ProductVendor  
    REBUILD WITH (MAXDOP=8);   
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [ALTER INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/alter-index-transact-sql.md).  
  
#### So legen Sie den maximalen Grad an Parallelität für einen neuen Index fest  
  
1.  Stellen Sie im Objekt-Explorer ** **eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.  
  
2.  Klicken Sie in der Standardleiste auf **Neue Abfrage**.  
  
3.  Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    CREATE INDEX IX_ProductVendor_NewVendorID   
    ON Purchasing.ProductVendor (BusinessEntityID)  
    WITH (MAXDOP=8);  
    GO  
    ```  
  
 Weitere Informationen finden Sie unter [CREATE INDEX &#40;Transact-SQL&#41;](../../t-sql/statements/create-index-transact-sql.md).  
  
  