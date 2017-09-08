---
title: DBCC FLUSHAUTHCACHE (Transact-SQL) | Microsoft Docs
ms.custom:
- MSDN content
- MSDN - SQL DB
ms.date: 07/16/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- DBCC FLUSHAUTHCACHE
- FLUSHAUTHCACHE
- DBCC_FLUSHAUTHCACHE_TSQL
- FLUSHAUTHCACHE_TSQL
helpviewer_keywords:
- DBCC FLUSHAUTHCACHE
ms.assetid: 681ef31d-ceb9-4da5-86bf-bf1240df950f
caps.latest.revision: 11
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 3ba6a519ebcdbbc70bf19ec491539a3b07fb6c85
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="dbcc-flushauthcache-transact-sql"></a>DBCC FLUSHAUTHCACHE (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-xxxxxx-asdb-xxxx-xxx-md.md)]

Leert den Datenbankcache der Authentifizierung mit den Informationen zu Anmeldungen und Firewallregeln für den aktuellen Benutzerdatenbank [!INCLUDE[ssSDS](../../includes/sssds-md.md)]. Diese Anweisung gilt nicht für der logischen master-Datenbank, weil der master-Datenbank den physischen Speicher für die Informationen zu Anmeldungen und Firewall-Regeln enthält. Der Benutzer die Anweisung ausführt und andere derzeit verbundene Benutzer bleiben verbunden. (DBCC FLUSHAUTHCACHE wird derzeit nicht unterstützt für [!INCLUDE[ssSDW_md](../../includes/sssdw-md.md)].)
 
![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
  
```sql
DBCC FLUSHAUTHCACHE [ ; ]  
```  
  
## <a name="arguments"></a>Argumente  
Keine.
  
## <a name="remarks"></a>Hinweise  
Des authentifizierungscaches erstellt eine Kopie von Anmeldenamen und Firewallregeln für Server, die in der Masterdatenbank gespeichert sind und platziert sie im Arbeitsspeicher in der Benutzerdatenbank.  Da die Informationen zu Benutzern eigenständiger Datenbanken bereits in der Benutzerdatenbank gespeichert sind, sind eigenständige Datenbankbenutzer nicht Teil des authentifizierungscaches.
Ständig aktive Verbindungen zur [!INCLUDE[ssSDS](../../includes/sssds-md.md)] erneute Autorisierung erfordern (ausgeführt durch die [!INCLUDE[ssDE](../../includes/ssde-md.md)]) mindestens alle 10 Stunden. Die [!INCLUDE[ssDE](../../includes/ssde-md.md)] Versuche erneute Autorisierung mithilfe der ursprünglich gesendeten Kennwort- und kein Benutzer Eingabe ist erforderlich. Zur Verbesserung der Leistung beim Zurücksetzen eines Kennworts in [!INCLUDE[ssSDS](../../includes/sssds-md.md)], die Verbindung wird nicht sofort erneut authentifiziert, auch wenn die Verbindung aufgrund von Verbindungspooling zurückgesetzt wird. Dies unterscheidet sich vom Verhalten des lokalen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Wenn das Kennwort geändert wurde, da die Verbindung ursprünglich autorisiert wurde, muss die Verbindung beendet und eine neue Verbindung hergestellt werden mit dem neuen Kennwort. Ein Benutzer mit der KILL DATABASE CONNECTION-Berechtigung kann explizit eine Verbindung mit beenden [!INCLUDE[ssSDS](../../includes/sssds-md.md)] mithilfe der [KILL &#40; Transact-SQL &#41; ](../../t-sql/language-elements/kill-transact-sql.md) Befehl.
  
## <a name="permissions"></a>Berechtigungen  
Erfordert die [!INCLUDE[ssSDS](../../includes/sssds-md.md)] -Administratorkonto ein.
  
## <a name="example"></a>Beispiel  
Die folgende Anweisung löscht des authentifizierungscaches für die aktuelle Datenbank.
  
```sql
DBCC FLUSHAUTHCACHE;  
```  
  
## <a name="see-also"></a>Siehe auch  
[DBCC &#40;Transact-SQL&#41;](../../t-sql/database-console-commands/dbcc-transact-sql.md)
  
  
