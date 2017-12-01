---
title: Sys.syslogins (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 09/08/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-compatibility-views
ms.reviewer: 
ms.suite: sql
ms.technology: database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- syslogins_TSQL
- syslogins
- sys.syslogins
- sys.syslogins_TSQL
dev_langs: TSQL
helpviewer_keywords:
- sys.syslogins compatibility view
- syslogins system table
ms.assetid: 4cb34f17-a4bb-469f-a218-71f074e6308f
caps.latest.revision: "41"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: On Demand
ms.openlocfilehash: ea9ceaa622c6ad7b39bed9c3e3d2439e56a57210
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="syssyslogins-transact-sql"></a>sys.syslogins (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Enthält eine Zeile für jedes Anmeldekonto.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
**Gilt für**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ([!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] bis zur [aktuellen Version](http://go.microsoft.com/fwlink/p/?LinkId=299658)).  
  
|Spaltenname|Datentyp|Description|  
|-----------------|---------------|-----------------|  
|**SID**|**varbinary (85)**|Sicherheits-ID.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**CREATEDATE**|**datetime**|Datum, an dem der Anmeldename hinzugefügt wurde.|  
|**updateDate**|**datetime**|Datum, an dem der Anmeldename aktualisiert wurde.|  
|**accdate**|**datetime**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**totcpu**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**totio**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**spacelimit**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**Timelimit**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**resultlimit**|**int**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**name**|**sysname**|Anmeldename des Benutzers.|  
|**dbname**|**sysname**|Name der Standarddatenbank des Benutzers beim Herstellen einer Verbindung.|  
|**Kennwort**|**vom Datentyp nvarchar(128)**|Gibt NULL zurück.|  
|**Sprache**|**sysname**|Standardsprache des Benutzers.|  
|**denylogin**|**int**|1 = Anmeldename ist ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Benutzer oder eine Windows-Gruppe, dem bzw. der der Zugriff verweigert wurde.|  
|**HasAccess**|**int**|1 = Dem Anmeldenamen wurde der Zugriff auf den Server erteilt.|  
|**isntname**|**int**|1 = Anmeldename ist ein Windows-Benutzer oder eine Windows-Gruppe.<br /><br /> 0 = Anmeldename ist ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldename.|  
|**isntgroup**|**int**|1 = Anmeldename ist eine Windows-Gruppe.|  
|**isntuser**|**int**|1 = Anmeldename ist ein Windows-Benutzer.|  
|**sysadmin**|**int**|1 = Der Anmeldename ist ein Mitglied der **sysadmin** -Serverrolle.|  
|**securityadmin**|**int**|1 = Der Anmeldename ist ein Mitglied der **securityadmin** -Serverrolle.|  
|**serveradmin**|**int**|1 = Der Anmeldename ist ein Mitglied der **serveradmin** -Serverrolle.|  
|**setupadmin**|**int**|1 = Der Anmeldename ist ein Mitglied der **setupadmin** -Serverrolle.|  
|**processadmin**|**int**|1 = Der Anmeldename ist ein Mitglied der **processadmin** -Serverrolle.|  
|**diskadmin**|**int**|1 = Der Anmeldename ist ein Mitglied der **diskadmin** -Serverrolle.|  
|**dbcreator**|**int**|1 = Der Anmeldename ist ein Mitglied der **dbcreator** -Serverrolle.|  
|**bulkadmin**|**int**|1 = Der Anmeldename ist ein Mitglied der festen Serverrolle **bulkadmin** .|  
|**LoginName**|**vom Datentyp nvarchar(128)**|Anmeldename des Benutzers. Dieser Parameter wird aus Gründen der Abwärtskompatibilität bereitgestellt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von Systemtabellen zu Systemsichten &#40; Transact-SQL &#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Kompatibilitätssichten &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  