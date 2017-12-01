---
title: IHpublishercolumns (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-tables
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- IHpublishercolumns
- IHpublishercolumns_TSQL
dev_langs: TSQL
helpviewer_keywords: IHpublishercolumns system table
ms.assetid: a5347750-224c-40d9-ae12-57e7213b7db9
caps.latest.revision: "24"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 94804f224c1807d709efb75960b6b677a068dda4
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihpublishercolumns-transact-sql"></a>IHpublishercolumns (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Die **IHpublishercolumns** -Systemtabelle stellt auf dem Verleger gespeicherte Metadaten dar. Diese Tabelle enthält eine Zeile für jede Spalte, die von nicht - SQL Server-Verlegern mithilfe des aktuellen Verteilers repliziert. Datentypinformationen in **IHpublishercolumns** bezieht sich auf die SQL Server - Datenbank-Managementsystem (DBMS) aus dem die veröffentlichten Daten. Diese Tabelle wird in der Verteilungsdatenbank gespeichert.  
  
## <a name="definition"></a>Definition  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**publishercolumn_id**|**int**|Identifiziert eine veröffentlichte Spalte.|  
|**table_id**|**int**|Identifiziert die Quelltabelle aus [IHpublishertables](../../relational-databases/system-tables/ihpublishertables-transact-sql.md) zu dem die Spalte gehört.|  
|**publisher_id**|**smallint**|Identifiziert den nicht - SQL Server-Verleger aus der die Spalte veröffentlicht wird.|  
|**name**|**sysname**|Der Name der veröffentlichten Spalte.|  
|**column_ordinal**|**int**|Identifiziert die Spalte nach Reihenfolge.|  
|**Typ**|**varchar(255)**|Der Spaltendatentyp der Quellspalte auf dem Verleger.|  
|**Länge**|**bigint**|Die Länge der Quellspalte auf dem Verleger.|  
|**prec**|**int**|Die Genauigkeit der Quellspalte auf dem Verleger.|  
|**Skalierung**|**int**|Die Dezimalstellen der Quellspalte auf dem Verleger.|  
|**IsNullable**|**bit**|Gibt an, ob die Spalte NULL-Werte zulässt, in denen **1** bedeutet, dass NULL-Werte akzeptiert werden.|  
|**iscaptured**|**bit**|Zeigt an, ob für die Spalte ein Trigger vorhanden ist. Ein Trigger kann auch dann vorhanden sein, wenn die Spalte nicht in einem Artikel veröffentlicht wird. Der Wert **1** bedeutet, die der Trigger für die Spalte vorhanden ist.|  
  
## <a name="see-also"></a>Siehe auch  
 [Heterogene Datenbankreplikation](../../relational-databases/replication/non-sql/heterogeneous-database-replication.md)   
 [Replikationstabellen &#40; Transact-SQL &#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Replikationssichten &#40; Transact-SQL &#41;](../../relational-databases/system-views/replication-views-transact-sql.md)   
 [Sysarticlecolumns &#40; Systemsicht &#41; &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysarticlecolumns-system-view-transact-sql.md)   
 [Sysarticlecolumns &#40; Transact-SQL &#41;](../../relational-databases/system-tables/sysarticlecolumns-transact-sql.md)  
  
  