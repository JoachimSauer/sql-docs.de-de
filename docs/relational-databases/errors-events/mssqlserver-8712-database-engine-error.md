---
title: MSSQLSERVER_8712 | Microsoft-Dokumentation
ms.custom: 
ms.date: 04/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
helpviewer_keywords:
- 8712 (Database Engine error)
ms.assetid: 292fb3bc-062e-41e4-a566-b5d3d0b21977
caps.latest.revision: 12
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: Human Translation
ms.sourcegitcommit: 2edcce51c6822a89151c3c3c76fbaacb5edd54f4
ms.openlocfilehash: 65489fa755c5dda3459d7de227631591f821e5bd
ms.contentlocale: de-de
ms.lasthandoff: 06/22/2017

---
# <a name="mssqlserver8712"></a>MSSQLSERVER_8712
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|8712|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|USEPLAN_ERR_NO_INDEX|  
|Meldungstext|Der im USE PLAN-Hinweis angegebene Index '%.*ls' ist nicht vorhanden. Geben Sie einen vorhandenen Index an, oder erstellen Sie einen Index mit dem angegebenen Namen.|  
  
## <a name="explanation"></a>Erklärung  
Ein im USE PLAN-Hinweis angegebener Index ist nicht vorhanden.  
  
## <a name="user-action"></a>Benutzeraktion  
Stellen Sie sicher, dass alle im USE PLAN-Hinweis angegebenen Indizes vorhanden sind.  
  
## <a name="see-also"></a>Siehe auch  
[Abfragehinweise &#40;Transact-SQL&#41;](~/t-sql/queries/hints-transact-sql-query.md)  
[Planhinweislisten](~/relational-databases/performance/plan-guides.md)  
  
