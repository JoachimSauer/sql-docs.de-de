---
title: Sp_changeqreader_agent (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: system-stored-procedures
ms.reviewer: 
ms.suite: sql
ms.technology: replication
ms.tgt_pltfrm: 
ms.topic: language-reference
applies_to: SQL Server
f1_keywords:
- sp_changeqreader_agent_TSQL
- sp_changeqreader_agent
helpviewer_keywords: sp_changeqreader_agent
ms.assetid: d3fe79c5-31ef-4565-bf38-b476b5fb16f7
caps.latest.revision: "21"
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: Inactive
ms.openlocfilehash: 0ce63f317910d84aae14f2457f383bce7ba291c1
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="spchangeqreaderagent-transact-sql"></a>sp_changeqreader_agent (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Ändert die Sicherheitseigenschaften eines Warteschlangenlese-Agents. Diese gespeicherte Prozedur wird auf dem Verteiler für die Verteilungsdatenbank oder auf dem Verleger für die Veröffentlichungsdatenbank ausgeführt.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
sp_changeqreader_agent [ [ @job_login = ] 'job_login' ]  
    [ , [ @job_password = ] 'job_password' ]  
    [ , [ @frompublisher = ] frompublisher   
```  
  
## <a name="arguments"></a>Argumente  
 [  **@job_login** =] **"***Job_login***"**  
 Der Anmeldename für das [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Konto, unter dem der Agent ausgeführt wird. *Job_login* ist **nvarchar(257)**, hat den Standardwert NULL.  
  
 [  **@job_password** =] **"***Job_password***"**  
 Das Kennwort für das Windows-Konto, unter dem der Agent ausgeführt wird. *Job_password* ist **Sysname**, hat den Standardwert NULL.  
  
 [  **@frompublisher=** ] *Frompublisher*  
 Gibt an, ob die Prozedur auf dem Verleger ausgeführt wird. *Frompublisher* bit und hat den Standardwert des **0**. Der Wert **1** bedeutet, dass die Prozedur auf dem Verleger für die Veröffentlichungsdatenbank ausgeführt wird.  
  
## <a name="return-code-values"></a>Rückgabecodewerte  
 **0** (Erfolg) oder **1** (Fehler)  
  
## <a name="remarks"></a>Hinweise  
 **Sp_changeqreader_agent** wird bei der Transaktionsreplikation verwendet.  
  
 **Sp_changeqreader_agent** wird verwendet, um das Windows-Konto zu ändern, unter dem ein Warteschlangenlese-Agent ausgeführt wird. Sie können das Kennwort für einen vorhandenen Windows-Anmeldenamen ändern oder einen neuen Windows-Anmeldenamen und ein neues Kennwort angeben.  
  
 Nach dem Ändern des Anmeldenamens oder Kennworts eines Agents müssen Sie den Agent beenden und neu starten, damit die Änderungen in Kraft treten.  
  
## <a name="permissions"></a>Berechtigungen  
 Nur Mitglieder der **Sysadmin** -Serverrolle kann ausführen **Sp_changeqreader_agent**.  
  
## <a name="see-also"></a>Siehe auch  
 [Anzeigen und Ändern von Replikationssicherheitseinstellungen](../../relational-databases/replication/security/view-and-modify-replication-security-settings.md)   
 [sp_addqreader_agent &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-addqreader-agent-transact-sql.md)  
  
  