---
title: "Tabelle kopieren oder Datenbank abfragen (SQL Server-Import/Export-Assistent) | Microsoft Docs"
ms.custom: ""
ms.date: "02/17/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.impexpwizard.specifytablecopyorquery.f1"
ms.assetid: 08aa7158-40e6-4ef3-84d3-1265a8ba194c
caps.latest.revision: 69
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 65
---
# Tabelle kopieren oder Datenbank abfragen (SQL Server-Import/Export-Assistent)
  Nachdem Sie Informationen zum Ziel Ihrer Daten bereitgestellt haben und darüber, wie Sie eine Verbindung mit ihnen herstellen, zeigt der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Import/Export-Assistent **Tabelle kopieren oder Datenbank abfragen** an. Wählen Sie auf dieser Seite eine der folgenden Optionen aus.
-   **Daten aus mindestens einer Tabelle oder Sicht kopieren**
-   **Abfrage zum Angeben der zu übertragenden Daten schreiben**
    
> [!TIP] Wenn Sie mehrere Datenbanken oder andere Datenbankobjekte als Tabellen und Sichten kopieren müssen, verwenden Sie anstelle des Import/Export-Assistenten den Assistenten zum Kopieren von Datenbanken. Weitere Informationen finden Sie unter [Verwenden des Assistenten zum Kopieren von Datenbanken](../../relational-databases/databases/use-the-copy-database-wizard.md).     
 
## <a name="screen-shot-of-the-specify-table-copy-or-query-page"></a>Screenshot der Seite Tabelle kopieren oder Datenbank abfragen    
 Die folgende Anzeige stellt die Seite **Tabelle kopieren oder Datenbank Abfragen** des Assistenten dar.    
    
 ![Table copy or query page of the Import and Export Wizard](../../integration-services/import-export-data/media/table-copy-or-query.png "Table copy or query page of the Import and Export Wizard")    
    
## <a name="specify-whether-to-copy-an-entire-table-or-write-a-query"></a>Angeben, ob eine gesamte Tabelle kopiert oder eine Abfrage geschrieben werden soll 
 **Daten aus mindestens einer Tabelle oder Sicht kopieren**    
 Verwenden Sie diese Option, wenn Sie alle Quelldaten ohne Filtern oder Ordnen der Datensätze kopieren möchten. Nachdem Sie auf **Weiter** geklickt haben, wählen Sie auf der Seite **Quelltabellen und -sichten auswählen** die zu kopierenden Tabellen aus. Weitere Informationen finden Sie unter [Quelltabellen und -sichten auswählen](../../integration-services/import-export-data/select-source-tables-and-views-sql-server-import-and-export-wizard.md).    

Wenn Sie die Option **Daten aus mindestens einer Tabelle oder Sicht kopieren** auswählen, können Sie aus einer Tabelle oder Sicht in eine Zieltabelle oder aus mehreren Tabellen oder Sichten in mehrere Zieltabellen kopieren.    
    
 **Abfrage zum Angeben der zu übertragenden Daten schreiben**    
 Wählen Sie diese Option aus, wenn Sie die Quelldaten filtern oder sortieren möchten, bevor Sie sie in den Zielort kopieren. Nachdem Sie auf **Weiter** geklickt haben, geben Sie eine SQL-Anweisung an, um im Dialogfeld **Quellabfrage angeben** Spalten anzugeben und Zeilen auszuwählen. Weitere Informationen finden Sie unter [Quellabfrage angeben](../../integration-services/import-export-data/provide-a-source-query-sql-server-import-and-export-wizard.md).    
    
Wenn Sie die Option **Abfrage zum Angeben der zu übertragenden Daten schreiben** auswählen, können Sie nur die Ergebnisse einer Abfrage in eine Zieltabelle kopieren.    
    
## <a name="why-isnt-the-copy-option-available"></a>Warum ist die Option zum Kopieren nicht verfügbar?    
 Die Option **Daten aus mindestens einer Tabelle oder Sicht kopieren** ist unter Umständen nicht verfügbar, wenn der Assistent einen [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Datenanbieter verwendet, um eine Verbindung mit Ihrer Datenquelle herzustellen. Dies geschieht, wenn der Assistent nicht über genügend Informationen zum Anfordern einer Liste von Tabellen und Sichten aus der Datenquelle verfügt.    
    
 Die Option **Daten aus mindestens einer Tabelle oder Sicht kopieren** ist nur für Anbieter verfügbar, die über einen ProviderDescription-Abschnitt in der Datei „ProviderDescriptors.xml“ verfügen. (Standardmäßig befindet sich diese Datei unter \<*Laufwerk*>:\Programme\Microsoft SQL Server\130\DTS\ProviderDescriptors.) Jeder ProviderDescription-Abschnitt in dieser Datei enthält die Informationen, die erforderlich sind, um Metadaten von dem entsprechenden Anbieter abzurufen.    
    
 Standardmäßig enthält die Datei „ProviderDescriptors.xml“ nur für die Anbieter in der folgenden Liste einen ProviderDescription-Abschnitt.    
    
-   .NET Framework-Datenanbieter für SQL Server (System.Data.SqlClient)    
    
-   .NET Framework-Datenanbieter für Oracle (System.Data.OracleClient)    
    
-   .NET Framework-Datenanbieter für ODBC (System.Data.Odbc)    
    
-    System.Data.OleDb (bezieht sich auf alle OLE DB-Anbieter)    
    
-   Microsoft-Anbieter für DB2, installiert von Microsoft Host Integration Server (Microsoft.HostIntegration.MsDb2Client.MsDb2Connection)    
    
 Drittanbieterentwickler können die Option **Daten aus mindestens einer Tabelle oder Sicht kopieren** für ihren Anbieter verfügbar machen, indem sie der Datei „ProviderDescriptors.xml“ einen ProviderDescriptor-Abschnitt hinzufügen. Öffnen Sie die Schemadatei „ProviderDescriptors.xsd“, die sich standardmäßig im selben Ordner befindet wie die Datei „ProviderDescriptors.xml“, um die Anforderungen für den ProviderDescriptor-Abschnitt zu prüfen.    
    
## <a name="whats-next"></a>Wie geht es weiter?    
 Nachdem Sie angegeben haben, ob Sie eine gesamte Tabelle kopieren oder eine Abfrage bereitstellen möchten, hängt die nächste Seite von der Option ab, die Sie auf dieser Seite ausgewählt haben sowie von dem Zielort Ihrer Daten.    
    
-   Wenn Sie **Daten aus mindestens einer Tabelle oder Sicht kopieren** ausgewählt haben, ist für die meisten Zielorte die nächste Seite **Quelltabellen und -sichten auswählen**. Auf dieser Seite wählen Sie die vorhandenen Tabellen und Sichten aus, die aus der Datenquelle in das Ziel kopiert werden sollen. Weitere Informationen finden Sie unter [Quelltabellen und -sichten auswählen](../../integration-services/import-export-data/select-source-tables-and-views-sql-server-import-and-export-wizard.md).    
    
-   Wenn Sie **Daten aus mindestens einer Tabelle oder Sicht kopieren** ausgewählt haben und es sich bei Ihrem Ziel um eine Flatfile handelt, ist die nächste Seite **Flatfileziel konfigurieren**. Auf dieser Seite geben Sie Formatierungsoptionen für die Zielflatfile an. (Die nächste Seite nach der Konfiguration der Flatfile ist anschließend **Quelltabellen und -sichten auswählen**.) Weitere Informationen finden Sie unter [Flatfileziel konfigurieren](../../integration-services/import-export-data/configure-flat-file-destination-sql-server-import-and-export-wizard.md).    
    
-   Wenn Sie **Abfrage zum Angeben der zu übertragenden Daten schreiben** ausgewählt haben, ist die nächste Seite **Quellabfrage eingeben**. Auf dieser Seite schreiben und testen Sie die SQL-Anweisung, die die Daten sammelt, die aus der Datenquelle in das Ziel kopiert werden sollen. (Die nächste Seite nach der Eingabe einer Abfrage ist anschließend **Quelltabellen und -sichten auswählen**.) Weitere Informationen finden Sie unter [Quellabfrage angeben](../../integration-services/import-export-data/provide-a-source-query-sql-server-import-and-export-wizard.md).    