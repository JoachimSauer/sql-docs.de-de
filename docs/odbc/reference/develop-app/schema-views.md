---
title: Schemaansichten | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- schema views [ODBC]
- functions [ODBC], catalog functions
- catalog functions [ODBC], schema views
ms.assetid: f1dfb3e8-a7bd-46c3-92b6-c19531e8409d
caps.latest.revision: 5
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 686b13ff9b480a1e2e96a175fe546d064079d871
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="schema-views"></a>Schema-Ansichten
Eine Anwendung kann Metadateninformationen aus dem DBMS durch Aufrufen von ODBC-Katalogfunktionen oder INFORMATION_SCHEMA-Sichten abzurufen. Die Ansichten werden gemäß dem ANSI SQL-92-Standard definiert.  
  
 Falls vom DBMS und der Treiber unterstützt, können der INFORMATION_SCHEMA-Sichten leistungsfähigere und umfassende Abrufen von Metadaten als die ODBC-Katalogfunktionen bieten. Eine Anwendung kann einen eigenen benutzerdefinierten ausführen **wählen** -Anweisung für eine dieser Ansichten können Ansichten zu verbinden oder eine Union für Sichten durchführen. Beim Angebots größer Hilfsprogramm und eine größere Anzahl an Metadaten werden INFORMATION_SCHEMA-Sichten nicht häufig vom DBMS unterstützt. Dies kann ändern, wie die Kompatibilität mit SQL-92 Weitere DBMS und-Treiber erreichen.  
  
 Um zu bestimmen, welche Ansichten unterstützt werden, eine Anwendung ruft **SQLGetInfo** mit der Option SQL_INFO_SCHEMA_VIEWS. Zum Abrufen von Metadaten aus einer unterstützten Sicht führt die Anwendung eine **wählen** Anweisung, der angibt, die Schemainformationen, die erforderlich sind.
