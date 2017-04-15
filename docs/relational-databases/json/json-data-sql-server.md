---
title: "JSON-Daten (SQL Server) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "01/31/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dbe-json"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
helpviewer_keywords: 
  - "JSON"
  - "JSON, integrierte Unterstützung"
ms.assetid: c9a4e145-33c3-42b2-a510-79813e67806a
caps.latest.revision: 47
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 44
---
# JSON-Daten (SQL Server)
[!INCLUDE[tsql-appliesto-ss2016-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2016-asdb-xxxx-xxx-md.md)]

  JSON ist ein beliebtes Textdatenformat zum Austauschen von Daten in modernen Webanwendungen und mobilen Anwendungen. JSON wird auch zum Speichern von unstrukturierten Daten in Protokolldateien oder NoSQL-Datenbanken wie Microsoft Azure DocumentDB verwendet. Viele REST-Webdienste geben Ergebnisse als JSON-Text formatiert zurück oder akzeptieren Daten, die im JSON-Format formatiert sind. Die meisten Azure-Dienste wie Azure Search, Azure Storage und Azure DocumentDb verfügen über REST-Endpunkte, die JSON zurückgeben oder verarbeiten. JSON ist auch das hauptsächliche Format zum Austauschen von Daten zwischen Webseiten und Webservern mithilfe von AJAX-Aufrufen.  
  
 Beispiel für JSON-Text:  
  
```json  
[   
   { "name": "John", "skills":["SQL","C#","Azure"] },  
   { "name": "Jane", "surname": "Doe" }  
]  
```  
  
 SQL Server bietet integrierte Funktionen und Operatoren, mit denen Sie die folgenden Schritte ausführen können.  
  
-   Analysieren Sie JSON-Text und lesen oder ändern Sie Werte.  
  
-   Wandeln Sie Arrays von JSON-Objekten in das Tabellenformat um.  
  
-   Wenden Sie eine beliebige Transact-SQL-Abfrage auf die konvertierte JSON-Objekte an.  
  
-   Formatieren Sie die Ergebnisse der Transact-SQL-Abfragen in das JSON-Format.  
  
 ![Overview of built-in JSON support](../../relational-databases/json/media/jsonslides1overview.png "Overview of built-in JSON support")  
  
 Hier sind die wichtigsten Funktionen, die SQL Server bietet.  
  
 **Extrahieren von Werten aus JSON-Text und Verwenden dieser Werte in Abfragen.** Wenn Sie JSON-Text verwenden, der in Datenbanktabellen gespeichert wird, können Sie integrierte Funktionen verwenden, um Werte im JSON-Text zu lesen oder zu ändern.  
  
-   Verwenden Sie die **JSON_VALUE**-Funktion, um einen skalaren Wert aus einer JSON-Zeichenfolge zu extrahieren.  
  
-   Verwenden Sie **JSON_QUERY**, um ein Objekt oder ein Array zu extrahieren.  
  
-   Verwenden Sie die **ISJSON**-Funktion zum Testen, ob eine Zeichenfolge ein gültiges JSON-Format enthält.  
  
 Im folgenden Beispiel verwendet die Abfrage sowohl relationale als auch JSON-Daten (gespeichert in der Spalte jsonCol) aus einer Tabelle:  
  
```tsql  
  
SELECT Name, Surname,     
    JSON_VALUE(jsonCol, '$.info.address.PostCode') as PostCode,  
    JSON_VALUE(jsonCol, '$.info.address."Address Line 1"') +  ' ' + JSON_VALUE(jsonCol, '$.info.address."Address Line 2"') AS Address,  
    JSON_QUERY(jsonCol, '$.info.skills') as Skills  
FROM PeopleCollection  
WHERE ISJSON(jsonCol) > 0   
  AND JSON_VALUE(jsonCol, '$.info.address.town') = 'Belgrade'  
  AND Status = 'Active'  
ORDER BY JSON_VALUE(@jsonInfo, '$.info.address.PostCode')  
  
```  
  
 Anwendungen und Tools erkennen keinen Unterschied zwischen den Werten aus skalaren Tabellenspalten und denen aus JSON-Spalten. Sie können Werte aus dem JSON-Text in jedem Teil der Transact-SQL-Abfrage verwenden (z.B. WHERE-, ORDER BY-, GROUP BY-Klauseln, Fenster-Aggregate usw.). JSON-Funktionen verwenden eine JavaScript-ähnliche Syntax zum Verweisen auf Werte in JSON-Text. Weitere Informationen finden Sie unter [Validate, Query, and Change JSON Data with Built-in Functions &#40;SQL Server&#41;](../../relational-databases/json/validate-query-and-change-json-data-with-built-in-functions-sql-server.md) (Überprüfen, Abfragen und Ändern von JSON-Daten mit integrierten Funktionen [SQL Server]), [JSON_VALUE &#40;Transact-SQL&#41;](../../t-sql/functions/json-value-transact-sql.md) und [JSON_QUERY &#40;Transact-SQL&#41;](../../t-sql/functions/json-query-transact-sql.md).  
  
 **Ändern Sie JSON-Werte.** Wenn Sie Teile des JSON-Texts ändern müssen, können Sie die **JSON_MODIFY**-Funktion verwenden, um den Wert einer Eigenschaft in einer JSON-Zeichenfolge zu aktualisieren und die aktualisierte JSON-Zeichenfolge zurückzugeben. Im folgenden Beispiel wird der Wert einer Eigenschaft in einer Variable aktualisiert, die JSON enthält.  
  
```tsql  
SET @jsonInfo = JSON_MODIFY(@jsonInfo, '$.info.address[0].town', 'London')  
```  
  
 **Konvertieren Sie JSON-Sammlungen in ein Rowset.** Eine benutzerdefinierte Abfragesprache ist zur Abfrage von JSON-Daten in SQL Server nicht erforderlich. Zum Abfragen von JSON-Daten können Sie Standard-T-SQL verwenden. Wenn Sie eine Abfrage erstellen oder JSON-Daten protokollieren müssen, können Sie die JSON-Daten einfach durch Aufrufen der **OPENJSON**-Rowsetfunktion in Zeilen und Spalten konvertieren. Verwenden Sie die **OPENJSON**-Funktion zum Importieren von JSON-Daten in SQL Server oder zum Konvertieren von JSON-Daten in Zeilen und Spalten. Weitere Informationen finden Sie unter [Convert JSON Data to Rows and Columns with OPENJSON &#40;SQL Server&#41;](../../relational-databases/json/convert-json-data-to-rows-and-columns-with-openjson-sql-server.md) (Konvertieren von JSON-Daten in Zeilen und Spalten mit OPENJSON [SQL Server]).  
  
 Im folgenden Beispiel wird **OPENJSON** aufgerufen, um ein Array von Objekten, das in einer **@json**-Variable gespeichert wird, in ein Rowset zu transformieren, das mithilfe der SQL SELECT-Standardanweisung abgefragt werden kann:  
  
```tsql  
SET @json =  
N'[  
      { "id" : 2,"info": { "name": "John", "surname": "Smith" }, "age": 25 },  
      { "id" : 5,"info": { "name": "Jane", "surname": "Smith" }, "dob": "2005-11-04T12:00:00" }  
]'  
  
SELECT *  
FROM OPENJSON(@json)  
 WITH (id int 'strict $.id',  
       firstName nvarchar(50) '$.info.name', lastName nvarchar(50) '$.info.surname',  
       age int, dateOfBirth datetime2 '$.dob')  
  
```  
  
 **Ergebnisse**  
  
|id|firstName|lastName|age|dateOfBirth|  
|--------|---------------|--------------|---------|-----------------|  
|2|John|Smith|25||  
|5|Jane|Smith||2005-11-04T12:00:00|  
  
 **OPENJSON** transformiert das Array von JSON-Objekten in eine Tabelle, wobei jedes Objekt als eine Zeile dargestellt wird. Die Schlüssel/Wert-Paare werden als Zellen zurückgegeben. **OPENJSON** konvertiert JSON-Werte in die angegebenen Typen. **OPENJSON** kann sowohl einfache Schlüssel/Wert-Paare als auch geschachtelte, hierarchisch angeordnete Objekte verarbeiten. Sie müssen nicht alle im JSON-Text enthaltenen Felder zurückgeben. **OPENJSON** gibt NULL-Werte zurück, wenn JSON-Werte nicht vorhanden sind. Sie können optional einen Pfad zu der Typspezifikation angeben, um auf eine geschachtelte Eigenschaft zu verweisen, oder um mit einem anderen Namen auf eine Eigenschaft zu verweisen. Das optionale **strenge** im Pfad gibt an, dass die Werte für die angegebenen Eigenschaften im JSON-Text vorhanden sein müssen. Weitere Informationen finden Sie unter [Convert JSON Data to Rows and Columns with OPENJSON &#40;SQL Server&#41;](../../relational-databases/json/convert-json-data-to-rows-and-columns-with-openjson-sql-server.md) (Konvertieren von JSON-Daten in Zeilen und Spalten mit OPENJSON [SQL Server]) und [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md).  
  
 **Konvertieren von SQL Server-Daten in JSON oder Exportieren von JSON.** Formatieren Sie Daten aus SQL Server oder die Ergebnisse von SQL-Abfragen im JSON-Format, indem Sie die **FOR JSON**-Klausel einer **SELECT**-Anweisung hinzufügen. Verwenden Sie FOR JSON, um die Formatierung der JSON-Ausgabe von den Clientanwendungen an SQL Server zu delegieren. Weitere Informationen finden Sie unter [Format Query Results as JSON with FOR JSON &#40;SQL Server&#41;](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md) (Formatieren von Abfrageergebnissen als JSON mit FOR JSON [SQL Server]).  
  
 Im folgenden Beispiel wird der PATH-Modus mit der FOR JSON-Klausel verwendet.  
  
```tsql  
SELECT id, firstName AS "info.name", lastName AS "info.surname", age, dateOfBirth as dob  
FROM People  
FOR JSON PATH  
```  
  
 Am   
Die     **FOR JSON**-Klausel formatiert SQL-Ergebnisse als JSON-Text, der für alle Apps bereitgestellt werden kann, die JSON verstehen. Die Option PATH verwendet in der SELECT-Klausel durch Punkte getrennte Aliase, um Objekte in den Abfrageergebnissen zu schachteln.  
  
 **Ergebnisse**  
  
```json  
[  
      { "id" : 2,"info": { "name": "John", "surname": "Smith" }, "age": 25 },  
      { "id" : 5,"info": { "name": "Jane", "surname": "Smith" }, "dob": "2005-11-04T12:00:00" }  
]  
```  
  
 Weitere Informationen finden Sie unter [Format Query Results as JSON with FOR JSON &#40;SQL Server&#41;](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md) (Formatieren von Abfrageergebnissen als JSON mit FOR JSON [SQL Server]) und [FOR-Klausel &#40;Transact-SQL&#41;](../Topic/FOR%20Clause%20\(Transact-SQL\).md).  
  
## Einsatzgebiete  
 SQL Server bietet ein Hybridmodell zum Speichern und Verarbeiten von relationalen Daten und JSON-Daten mithilfe der Transact-SQL-Standardsprache. Sie können Sammlungen Ihrer JSON-Dokumente nach Tabellen anordnen, Beziehungen zwischen ihnen herstellen, in Tabellen gespeicherte, stark typisierte Skalarspalten mit flexiblen Schlüssel-Wert/Paaren kombinieren, die in JSON-Spalten gespeichert werden, und sowohl Skalarwerte als auch JSON-Werte in einer oder mehreren Tabellen mithilfe von vollständigem Transact-SQL abfragen. JSON-Text wird in der Regel in „varchar“- oder „nvarchar“-Spalten gespeichert und als Nur-Text indiziert. Jede SQL Server-Funktion oder -Komponente, die Text unterstützt, unterstützt auch JSON, daher gibt es fast keine Einschränkungen hinsichtlich der Interaktion zwischen JSON und anderen SQL Server-Funktionen. Sie können JSON im Arbeitsspeicher oder in temporalen Tabellen speichern, Sicherheitsprädikate auf Zeilenebene auf JSON-Text anwenden usw. Wenn bei Ihnen reine JSON-Arbeitsauslastungen vorliegen, für die Sie eine Abfragesprache verwenden möchten, die der Verarbeitung von JSON-Dokumenten angepasst ist, sollten Sie Microsoft Azure [DocumentDB](https://azure.microsoft.com/services/documentdb/) in Erwägung ziehen.  
  
 Hier folgen einige Anwendungsfälle, die veranschaulichen, wie Sie die integrierte JSON-Unterstützung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwenden können.  
  
## Rückgabe von Daten aus einer SQL Server-Tabelle im JSON-Format  
 Wenn Sie einen Webdienst verwenden, der Daten von der Datenbankebene übernimmt und im JSON-Format oder in JavaScript-Frameworks oder -Bibliotheken (die Daten im JSON-Format akzeptieren) zurückgibt, können Sie die Ergebnisse direkt in einer SQL-Abfrage formatieren. Anstatt Code zu schreiben oder eine Bibliothek einzuschließen, um tabellarische Abfrageergebnisse zu konvertieren und dann Objekte in das JSON-Format zu serialisieren, können Sie auch FOR JSON verwenden, um die JSON-Formatierung an SQL Server zu delegieren.  
  
 Sie können z.B. eine JSON-Ausgabe generieren, die der OData-Spezifikation entspricht. Der Webdienst erwartet eine Anforderung und Antwort im folgenden Format.  
  
-   Anforderung: `/Northwind/Northwind.svc/Products(1)?$select=ProductID,ProductName`  
  
-   Antwort: `{"@odata.context":"http://services.odata.org/V4/Northwind/Northwind.svc/$metadata#Products(ProductID,ProductName)/$entity","ProductID":1,"ProductName":"Chai"}`  
  
 Diese OData-URL stellt eine Anforderung für die Spalten „ProductID“ und „ProductName“ für das Produkt mit der ID „1“. Sie können FOR JSON verwenden, um die Ausgabe erwartungsgemäß in SQL Server zu formatieren.  
  
```tsql  
SELECT 'http://services.odata.org/V4/Northwind/Northwind.svc/$metadata#Products(ProductID,ProductName)/$entity' AS '@odata.context',   
ProductID, Name as ProductName   
FROM Production.Product  
WHERE ProductID = 1  
FOR JSON AUTO  
  
```  
  
 Das Ergebnis dieser Abfrage ist ein vollständig mit der OData-Spezifikation kompatibler JSON-Text. Formatierung und Escapevorgang werden von SQL Server übernommen. SQL Server kann Abfrageergebnisse in einem beliebigen Format wie OData JSON oder GeoJSON formatieren. Weitere Informationen finden Sie unter [Returning spatial data in GeoJSON format](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2016/01/05/returning-spatial-data-in-geojson-format-part-1) (Zurückgeben von räumlichen Daten im GeoJSON-Format).  
  
## Analysieren von JSON-Daten mit SQL-Abfragen  
 Wenn Sie JSON-Daten für Berichtszwecke filtern oder aggregieren müssen, können Sie JSON mithilfe von OPENJSON in ein relationales Format transformieren. Verwenden Sie dann Standard-[!INCLUDE[tsql](../../includes/tsql-md.md)] und integrierte Funktionen, um die Berichte vorzubereiten.  
  
```tsql  
SELECT Tab.Id, SalesOrderJsonData.Customer, SalesOrderJsonData.Date  
FROM   SalesOrderRecord AS Tab  
         CROSS APPLY  
    OPENJSON (Tab.json, N'$.Orders.OrdersArray')  
          WITH (  
             Number   varchar(200) N'$.Order.Number',   
             Date     datetime     N'$.Order.Date',  
             Customer varchar(200) N'$.AccountNumber',   
             Quantity int          N'$.Item.Quantity'  
          )  
 AS SalesOrderJsonData  
WHERE JSON_VALUE(Tab.json, '$.Status') = N'Closed'  
ORDER BY JSON_VALUE(Tab.json, '$.Group'), Tab.DateModified  
  
```  
  
 Sowohl Standardtabellenspalten und -werte aus JSON-Text können in derselben Abfrage verwendet werden. Sie können Indizes zum Ausdruck „JSON_VALUE(Tab.json, '$.Status')“ hinzufügen, um die Abfrageleistung zu erhöhen.  
  
## Importieren von JSON-Daten in SQL Server-Tabellen  
 Wenn Sie JSON-Daten aus einem externen Dienst in SQL Server laden müssen, können Sie die Daten mit OPENJSON in SQL Server importieren, anstatt die Daten in der Anwendungsschicht zu analysieren.  
  
```tsql  
INSERT INTO SalesReport  
SELECT SalesOrderJsonData.*  
FROM OPENJSON (@jsonVariable, N'$.Orders.OrdersArray')  
          WITH (  
             Number   varchar(200) N'$.Order.Number',   
             Date     datetime     N'$.Order.Date',  
             Customer varchar(200) N'$.AccountNumber',   
             Quantity int          N'$.Item.Quantity'  
          )  
 AS SalesOrderJsonData;  
  
```  
  
 Der Inhalt der JSON-Variablen kann von einem externen REST-Dienst bereitgestellt, als Parameter von einem clientseitigen JavaScript-Framework gesendet oder aus externen Dateien geladen werden. Sie können Ergebnisse aus JSON-Text ganz einfach in eine SQL-Tabelle einfügen, dort aktualisieren oder zusammenführen. Weitere Informationen zu diesem Szenario finden Sie unter [OPENJSON – The easiest way to import JSON text into table](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2015/09/22/openjson-the-easiest-way-to-import-json-text-into-table/) (OPENJSON – der einfachste Weg, JSON-Text in Tabellen zu importieren), [Upsert JSON documents in SQL Server 2016](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2016/03/03/upsert-json-documents-in-sql-server-2016) (Upsert von JSON-Dokumenten in SQL Server 2016) und [Loading GeoJSON data into SQL Server 2016](https://blogs.msdn.microsoft.com/sqlserverstorageengine/2016/01/05/loading-geojson-data-into-sql-server/) (Laden von GeoJSON-Daten in SQL Server 2016).  
  
## Laden von JSON-Dateien in SQL Server  
 In Dateien gespeicherte Informationen können als Standard-JSON oder als JSON-Text formatiert werden, in dem Zeilenumbrüche als Trennzeichen verwendet werden. SQL Server kann die Inhalte aus JSON-Dateien importieren, mit OPENJSON oder JSON_VALUE-Funktionen analysieren und in Tabellen laden.  
  
 Wenn Ihre JSON-Dateien in lokalen Dateien, auf freigegebenen Netzlaufwerken oder einem Azure File Storage-Speicherort gespeichert werden, auf die SQL Server zugreifen kann, können Sie einen Massenimport durchführen, um die JSON-Daten in SQL Server zu laden. Weitere Informationen zu diesem Szenario finden Sie unter [Importing JSON files into SQL Server using OPENROWSET (BULK)](http://blogs.msdn.com/b/sqlserverstorageengine/archive/2015/10/07/importing-json-files-into-sql-server-using-openrowset-bulk.aspx) (Importieren von JSON-Dateien in SQL Server mithilfe von OPENROWSET [BULK]).  
  
 Wenn Ihre JSON-Dateien, die Zeilenumbrüche als Trennzeichen verwenden, in Azure-Blobspeicher oder im Hadoop-Dateisystem gespeichert werden, können Sie den JSON-Text mithilfe von Polybase laden, in Transact-SQL-Code analysieren und in Tabellen laden.  
  
## Testen der integrierten JSON-Unterstützung  
 **Testen Sie die integrierte JSON-Unterstützung mithilfe der AdventureWorks-Beispieldatenbank.** Laden Sie zum Abrufen der AdventureWorks-Beispieldatenbank zumindest die Datenbankdatei und die Beispiel- und Skriptdatei [here](https://www.microsoft.com/en-us/download/details.aspx?id=49502). Nach der Wiederherstellung der Beispieldatenbank auf einer Instanz von SQL Server 2016, entpacken Sie die Beispieldateien, und öffnen Sie die Datei „JSON Sample Queries procedures views and indexes.sql“ im JSON-Ordner. Führen Sie die Skripts in dieser Datei aus, um einige der vorhandenen Daten als JSON-Daten neu zu formatieren, führen Sie Beispielabfragen und -berichte für die JSON-Daten aus, indizieren Sie die JSON-Daten, und importieren und exportieren Sie JSON.  
  
 Mit den in der Datei enthaltenen Skripts haben Sie die folgenden Möglichkeiten.  
  
1.  Denormalisieren Sie die vorhandenen Schemas, um Spalten mit JSON-Daten zu erstellen.  
  
    1.  Speichern Sie Informationen aus den Tabellen „SalesReasons“, „SalesOrderDetails“, „SalesPerson“, „Customer“ sowie aus anderen Tabellen, die auftragsbezogene Daten enthalten, in der Tabelle „SalesOrder_json“ in JSON-Spalten.  
  
    2.  Speichern Sie Informationen aus den Tabellen „EmailAddresses“ bzw. „PersonPhone“ als Arrays von JSON-Objekten in der Tabelle „Person_json“.  
  
2.  Erstellen Sie Prozeduren und Sichten, die JSON-Daten abfragen.  
  
3.  Indizieren Sie JSON-Daten: Erstellen Sie Indizes zu JSON-Eigenschaften und Volltextindizes.  
  
4.  Importieren und exportieren Sie JSON: Erstellen Sie Prozeduren und führen Sie diese aus, die den Inhalt der Tabellen „Person“ und „SalesOrder“ als JSON-Ergebnisse exportieren und importieren sowie die Tabellen „Person“ und „SalesOrder“ mithilfe von JSON-Eingaben aktualisieren.  
  
5.  Führen Sie Abfragebeispiele aus: Führen Sie einige Abfragen aus, die die in den Schritten 2 und 4 erstellten gespeicherten Prozeduren und Sichten aufrufen.  
  
6.  Bereinigen Sie Skripts: Führen Sie diesen Teil nicht aus, wenn Sie die in den Schritten 2 und 4 erstellten gespeicherten Prozeduren und Sichten beibehalten möchten.  
  
## Weitere Informationen zur integrierten JSON-Unterstützung  
  
### Themen in diesem Abschnitt  
 [Format Query Results as JSON with FOR JSON &#40;SQL Server&#41; (Formatieren von Abfrageergebnissen als JSON mit FOR JSON [SQL Server])](../Topic/Format%20Query%20Results%20as%20JSON%20with%20FOR%20JSON%20\(SQL%20Server\).md)  
 Verwenden Sie die FOR JSON-Klausel, um die Formatierung der JSON-Ausgabe von Ihren Clientanwendungen an SQL Server zu delegieren.  
  
 [Convert JSON Data to Rows and Columns with OPENJSON &#40;SQL Server&#41; (Konvertieren von JSON-Daten in Zeilen und Spalten mit OPENJSON [SQL Server])](../Topic/Convert%20JSON%20Data%20to%20Rows%20and%20Columns%20with%20OPENJSON%20\(SQL%20Server\).md)  
 Verwenden Sie OPENJSON, um JSON-Daten in SQL Server zu importieren oder JSON-Daten für eine App oder einen Dienst in das relationale Format zu konvertieren, die JSON derzeit nicht direkt verarbeiten können, z. B. SQL Server Integration Services.  
  
 [Validate, Query, and Change JSON Data with Built-in Functions &#40;SQL Server&#41; (Überprüfen, Abfragen und Ändern von JSON-Daten mit integrierten Funktionen [SQL Server])](../Topic/Validate,%20Query,%20and%20Change%20JSON%20Data%20with%20Built-in%20Functions%20\(SQL%20Server\).md)  
 Verwenden Sie diese integrierten Funktionen, um JSON-Text zu überprüfen und einen Skalarwert, ein Objekt oder ein Array zu extrahieren.  
  
 [JSON Path Expressions &#40;SQL Server&#41; (JSON-Pfadausdrücke [SQL Server])](../Topic/JSON%20Path%20Expressions%20\(SQL%20Server\).md)  
 Verwenden Sie einen Pfadausdruck, um den zu verwendenden JSON-Text anzugeben.  
  
 [Indizieren von JSON-Daten](../../relational-databases/json/index-json-data.md)  
 Verwenden Sie berechnete Spalten, um für Eigenschaften in JSON-Dokumenten Indizes mit Sortierungserkennung zu erstellen.  
  
 [Häufig gestellte Fragen zu JSON in SQL Server](../Topic/Frequently%20Asked%20Questions%20about%20JSON%20in%20SQL%20Server.md)  
 Hier finden Sie Antworten auf einige häufig gestellte Fragen zu der integrierten JSON-Unterstützung in SQL Server.  
  
### Microsoft-Blogbeiträge  
  
-   [Blogeinträge von Jovan Popovic, Program Manager bei Microsoft](http://blogs.msdn.com/b/sqlserverstorageengine/archive/tags/json/)  
  
### Referenzthemen  
  
-   [FOR-Klausel &#40;Transact-SQL&#41;](../Topic/FOR%20Clause%20\(Transact-SQL\).md) (FOR JSON)  
  
-   [OPENJSON &#40;Transact-SQL&#41;](../../t-sql/functions/openjson-transact-sql.md)  
  
-   [JSON Functions &#40;Transact-SQL&#41; (JSON-Funktionen [Transact-SQL])](../Topic/JSON%20Functions%20\(Transact-SQL\).md)  
  
    -   [ISJSON &#40;Transact-SQL&#41;](../../t-sql/functions/isjson-transact-sql.md)  
  
    -   [JSON_VALUE &#40;Transact-SQL&#41;](../../t-sql/functions/json-value-transact-sql.md)  
  
    -   [JSON_QUERY &#40;Transact-SQL&#41;](../../t-sql/functions/json-query-transact-sql.md)  
  
    -   [JSON_MODIFY &#40;Transact-SQL&#41;](../../t-sql/functions/json-modify-transact-sql.md)  
  
  