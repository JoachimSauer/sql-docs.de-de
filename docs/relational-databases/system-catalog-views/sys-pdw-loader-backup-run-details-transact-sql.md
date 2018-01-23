---
title: Sys.pdw_loader_backup_run_details (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: 
ms.prod_service: sql-data-warehouse, pdw
ms.service: sql-data-warehouse
ms.component: system-catalog-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: TSQL
ms.assetid: 04fc004f-ee15-4d7a-be08-78357aa99b55
caps.latest.revision: "9"
author: barbkess
ms.author: barbkess
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 79e69b2a74841e790eb178aa2f8d1b693cfe7c5a
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="syspdwloaderbackuprundetails-transact-sql"></a>Sys.pdw_loader_backup_run_details (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-asdw-pdw-md.md)]

  Enthält weitere ausführliche Informationen über die Informationen in [sys.pdw_loader_backup_runs &#40; Transact-SQL &#41; ](../../relational-databases/system-catalog-views/sys-pdw-loader-backup-runs-transact-sql.md), Informationen zu laufenden und abgeschlossenen sicherungs- und Wiederherstellungsvorgänge in [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] und zur laufenden und abgeschlossenen Sicherung, Wiederherstellung und Ladevorgänge in [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]. Die Informationen, die über Systemneustarts weiterhin besteht.  
  
|Spaltenname|Datentyp|Description|Bereich|  
|-----------------|---------------|-----------------|-----------|  
|run_id|**int**|Eindeutiger Bezeichner für eine bestimmte Sicherung oder Wiederherstellung ausführen.<br /><br /> Run_id und Pdw_node_id bilden den Schlüssel für diese Ansicht ein.||  
|pdw_node_id|**int**|Eindeutige Bezeichner eines Knotens Einheit für die Details von diesen Eintrag enthält.<br /><br /> Run_id und Pdw_node_id bilden den Schlüssel für diese Ansicht ein.|Finden Sie unter "node_id" in [sys.dm_pdw_nodes &#40; Transact-SQL &#41; ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md).|  
|status|**nvarchar(16)**|Der aktuelle Status der Ausführung.|"ABGEBROCHEN", "ABGESCHLOSSEN", "FEHLGESCHLAGEN", "QUEUED", "WIRD AUSGEFÜHRT"|  
|start_time|**datetime**|Zeitpunkt, zu dem der Vorgang auf diesem bestimmten Knoten begonnen hat.||  
|end_time|**datetime**|Beendigungszeit der Vorgang auf diesem bestimmten Knoten, falls vorhanden.||  
|total_elapsed_time|**int**|Gesamtzeit der Vorgang auf diesem bestimmten Knoten ausgeführt wurde.|Wenn Total_elapsed_time den maximalen Wert für eine ganze Zahl (24.8 Tage in Millisekunden) überschreitet, führt es Materialisierung Fehler aufgrund einer dazu, dass "Überlauf".<br /><br /> Der maximale Wert in Millisekunden entspricht 24.8 Tage.|  
|Status|**int**|Status des Vorgangs als Prozentsatz ausgedrückt.|0 bis 100|  
  
## <a name="see-also"></a>Siehe auch  
 [SQL Datawarehouse und Parallel Datawarehouse-Katalogsichten](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)  
  
  