---
title: Geben Sie die Bezeichner | Microsoft Docs
ms.custom: 
ms.date: 01/19/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- drivers
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data types [ODBC], identifiers
- type identifiers [ODBC]
- identifiers [ODBC], type
- type identifiers [ODBC], about type identifiers
ms.assetid: 1d9fdfa2-e378-44fe-ac66-9743d9bbdd5a
caps.latest.revision: 9
author: MightyPen
ms.author: genemi
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f7e6274d77a9cdd4de6cbcaef559ca99f77b3608
ms.openlocfilehash: da01de66ee5b20d873b3b50ea24c72549174e90b
ms.contentlocale: de-de
ms.lasthandoff: 09/09/2017

---
# <a name="type-identifiers"></a>Typ-IDs
Um SQL- und C-Datentypen zu beschreiben, ODBC definiert zwei Sätze von *Typenbezeichner*. Ein Typbezeichner beschreibt den Typ der SQL-Spalte oder eine C-Puffer. Es ist ein **#define** Wert, und ist im Allgemeinen als ein Funktionsargument übergeben oder in Metadaten ausgegeben.  
  
 Beispielsweise beim folgenden Aufruf **SQLBindParameter** bindet eine Variable des Typs SQL_DATE_STRUCT an eine Date-Parameter in einer SQL­Anweisung. Der C-Typbezeichner SQL_C_TYPE_DATE gibt den Typ des der *Datum* Variable und die SQL-Typ-ID SQL_TYPE_DATE gibt den Typ des dynamischen Parameters.  
  
```  
SQL_DATE_STRUCT Date;  
SQLINTEGER  DateInd = 0;  
SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT, SQL_C_TYPE_DATE, SQL_TYPE_DATE, 0, 0,  
                  &Date, 0, &DateInd);  
```