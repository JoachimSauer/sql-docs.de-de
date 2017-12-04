---
title: Replikationssichten (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-views
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
dev_langs: TSQL
helpviewer_keywords:
- distribution databases [SQL Server replication], system views
- metadata [SQL Server], views
- views [SQL Server], replication
- replication views [SQL Server]
- publications [SQL Server replication], system views
- articles [SQL Server replication], system views
- replication metadata [SQL Server]
- subscriptions [SQL Server replication], system views
- system views [SQL Server], replication
ms.assetid: 93e5056d-0d93-4a48-ba33-72762eb995d8
caps.latest.revision: "14"
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: b73dfed7709b76d20856fe03648a7e0c6db0d258
ms.sourcegitcommit: 66bef6981f613b454db465e190b489031c4fb8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="replication-views-transact-sql"></a>Replikationssichten (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2012-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2012-xxxx-xxxx-xxx-md.md)]

  Diese Sichten enthalten Informationen, die von der Replikation in verwendet [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Die Sichten ermöglichen einen leichteren Zugriff auf Daten in [Replikationssystemtabellen](../../relational-databases/system-tables/replication-tables-transact-sql.md). Sichten werden in einer Benutzerdatenbank erstellt, wenn diese Datenbank als Veröffentlichungs- oder Abonnementdatenbank aktiviert wird. Wird die Datenbank aus der Replikationstopologie entfernt, dann werden auch alle Replikationsobjekte aus Benutzerdatenbanken entfernt. Die bevorzugte Methode für den Zugriff auf Replikationsmetadaten besteht, mithilfe von [gespeicherten Replikationsprozeduren](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md).  
  
> [!IMPORTANT]  
>  Systemsichten sollten von keinem Benutzer direkt geändert werden.  
  
## <a name="replication-views"></a>Replikationssichten  
 Im Folgenden wird eine Liste der von der Replikation verwendeten Systemsichten aufgeführt. Die Liste ist nach Datenbanken gruppiert.  
  
### <a name="replication-views-in-the-msdb-database"></a>Replikationssichten in der msdb-Datenbank  
  
|||  
|-|-|  
|[MSdatatype_mappings &#40; Transact-SQL &#41;](../../relational-databases/system-views/msdatatype-mappings-transact-sql.md)|[Sysdatatypemappings &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysdatatypemappings-transact-sql.md)|  
  
### <a name="replication-views-in-the-distribution-database"></a>Replikationssichten in der Verteilungsdatenbank  
  
|||  
|-|-|  
|[IHextendedArticleView &#40; Transact-SQL &#41;](../../relational-databases/system-views/ihextendedarticleview-transact-sql.md)|[Sysarticles &#40; Systemsicht &#41; &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysarticles-system-view-transact-sql.md)|  
|[IHextendedSubscriptionView &#40; Transact-SQL &#41;](../../relational-databases/system-views/ihextendedsubscriptionview-transact-sql.md)|[Sysextendedarticlesview &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysextendedarticlesview-transact-sql.md)|  
|[IHsyscolumns &#40; Transact-SQL &#41;](../../relational-databases/system-views/ihsyscolumns-transact-sql.md)|[syspublications &#40;Systemsicht&#41; &#40;Transact-SQL&#41;](../../relational-databases/system-views/syspublications-system-view-transact-sql.md)|  
|[MSdistribution_status &#40; Transact-SQL &#41;](../../relational-databases/system-views/msdistribution-status-transact-sql.md)|[syssubscriptions &#40;Systemsicht&#41; &#40;Transact-SQL&#41;](../../relational-databases/system-views/syssubscriptions-system-view-transact-sql.md)|  
|[Sysarticlecolumns &#40; Systemsicht &#41; &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysarticlecolumns-system-view-transact-sql.md)||  
  
### <a name="replication-views-in-the-publication-database"></a>Replikationssichten in der Veröffentlichungsdatenbank  
  
|||  
|-|-|  
|[Sysmergeextendedarticlesview &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysmergeextendedarticlesview-transact-sql.md)|[Sysmergepartitioninfoview &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysmergepartitioninfoview-transact-sql.md)|  
|[Systranschemas &#40; Transact-SQL &#41;](../../relational-databases/system-views/systranschemas-transact-sql.md)||  
  
### <a name="replication-views-in-the-subscription-database"></a>Replikationssichten in der Abonnementdatenbank  
  
|||  
|-|-|  
|[Sysmergeextendedarticlesview &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysmergeextendedarticlesview-transact-sql.md)|[Sysmergepartitioninfoview &#40; Transact-SQL &#41;](../../relational-databases/system-views/sysmergepartitioninfoview-transact-sql.md)|  
|[Systranschemas &#40; Transact-SQL &#41;](../../relational-databases/system-views/systranschemas-transact-sql.md)||  
  
## <a name="see-also"></a>Siehe auch  
 [Replikationstabellen &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)  
  
  