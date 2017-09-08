---
title: Local-Name-aus-QName (XQuery) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- XML
helpviewer_keywords:
- fn:local-name-from-QName function
- local-name-from-QName function
ms.assetid: fafed718-8c3c-403f-93ee-ec51fc157a6e
caps.latest.revision: 16
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 506a9923b8c74ecb022e6f3ba21305fb28ca49de
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="functions-related-to-qnames---local-name-from-qname"></a>Funktionen im Zusammenhang mit QNames - lokale Namen von QName
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx_md](../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Gibt einen xs: NCName, die den lokalen Anteil des vom angegebenen QName darstellt *$arg*. Das Ergebnis ist eine leere Sequenz, wenn *$arg* die leere Sequenz.  
  
## <a name="syntax"></a>Syntax  
  
```  
fn:local-name-from-QName($arg as xs:QName?) as xs:NCName?  
```  
  
## <a name="arguments"></a>Argumente  
 *$arg*  
 Der QName, aus dem der lokale Name extrahiert werden soll.  
  
## <a name="examples"></a>Beispiele  
 Dieses Thema stellt XQuery-Beispiele für XML-Instanzen, die in verschiedenen gespeichert sind **Xml** in Spalten vom Typ der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] Datenbank.  
  
 Im folgenden Beispiel wird die **local-name-from-QName()** Webparts-Funktion zum Abrufen des lokalen Namen und Namespace-URI von einem QName-Typ-Wert. Das Beispiel führt die folgenden Aktionen aus:  
  
-   Erstellen einer XML-Schemaauflistung.  
  
-   Erstellen einer Tabelle mit einer Spalte des Typs xml. Der xml-Typ wird mithilfe der XML-Schemaauflistung typisiert.  
  
-   Speichern einer XML-Beispielinstanz in der Tabelle. Mithilfe der **query()** Methode des XML-Datentyps, der Abfrageausdruck wird ausgeführt, um den lokalen namensanteil des Werts der QName-Typ aus der Instanz abzurufen.  
  
```  
DROP TABLE T  
go  
DROP XML SCHEMA COLLECTION SC  
go  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"  
targetNamespace="QNameXSD" >  
      <element name="root" type="QName" nillable="true"/>  
</schema>'  
go  
  
CREATE TABLE T (xmlCol XML(SC))  
go  
-- following OK  
insert into T values ('<root xmlns="QNameXSD" xmlns:a="http://someURI">a:someLocalName</root>')  
 go  
-- Retrieve the local name.   
SELECT xmlCol.query('declare default element namespace "QNameXSD"; local-name-from-QName(/root[1])')  
FROM T  
-- Result = someLocalName  
-- You can retrive namespace URI part from the QName using the namespace-uri-from-QName() function  
SELECT xmlCol.query('declare default element namespace "QNameXSD"; namespace-uri-from-QName(/root[1])')  
FROM T  
-- Result = http://someURI  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen, die im Zusammenhang mit QNames &#40; XQuery &#41;](http://msdn.microsoft.com/library/7e07eb26-f551-4b63-ab77-861684faff71)  
  
  