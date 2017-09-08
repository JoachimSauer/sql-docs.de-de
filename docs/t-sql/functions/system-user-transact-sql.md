---
title: SYSTEM_USER (Transact-SQL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SYSTEM_USER_TSQL
- SYSTEM_USER
dev_langs:
- TSQL
helpviewer_keywords:
- current user names
- system-supplied user names [SQL Server]
- users [SQL Server], logins
- logins [SQL Server], identification name
- current system user names
- SYSTEM_USER function
- inserting system user name into table
- system usernames [SQL Server]
- users [SQL Server], names
ms.assetid: 565984cd-60c6-4df7-83ea-2349b838ccb2
caps.latest.revision: 44
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d3f13d5db5d7787a60c455edc64644f4c23779fc
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="systemuser-transact-sql"></a>SYSTEM_USER (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-asdw-pdw_md](../../includes/tsql-appliesto-ss2008-xxxx-asdw-pdw-md.md)]

  Ermöglicht das Einfügen eines vom System bereitgestellten Werts für den aktuellen Anmeldenamen in eine Tabelle, wenn kein Standardwert angegeben ist.  
  
 ![Themenlinksymbol](../../database-engine/configure-windows/media/topic-link.gif "Topic link icon") [Transact-SQL Syntax Conventions (Transact-SQL-Syntaxkonventionen)](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
-- Syntax for SQL Server, Azure SQL Data Warehouse, Parallel Data Warehouse  
  
SYSTEM_USER  
```  
  
## <a name="return-types"></a>Rückgabetypen  
 **nchar**  
  
## <a name="remarks"></a>Hinweise  
 Sie können die SYSTEM_USER-Funktion mit DEFAULT-Einschränkungen in den Anweisungen CREATE TABLE und ALTER TABLE verwenden. Sie können sie auch wie jede beliebige Standardfunktion verwenden.  
  
 Unterscheiden sich Benutzer- und Anmeldename, gibt SYSTEM_USER den Anmeldenamen zurück.  
  
 Wenn der aktuelle Benutzer angemeldet ist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe der Windows-Authentifizierung, gibt SYSTEM_USER den Windows-Anmeldenamen im Format: *Domäne*\\*User_login_name*. Wenn der aktuelle Benutzer jedoch über die SQL Server-Authentifizierung bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] angemeldet ist, gibt SYSTEM_USER den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Anmeldenamen zurück, z. B. `WillisJo` für einen als `WillisJo` angemeldeten Benutzer.  
  
 SYSTEM_USER gibt den Namen des zurzeit ausgeführten Kontexts zurück. Wenn der Kontext mithilfe der EXECUTE AS-Anweisung gewechselt wurde, gibt SYSTEM_USER den Namen des Kontexts zurück, dessen Identität angenommen wurde.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-using-systemuser-to-return-the-current-system-user-name"></a>A. Verwenden von SYSTEM_USER zur Rückgabe des aktuellen Systembenutzernamens  
 Im folgenden Beispiel wird eine `char`-Variable deklariert, der aktuelle Wert von `SYSTEM_USER` in der Variablen gespeichert und dann der in der Variablen gespeicherte Wert ausgegeben.  
  
```  
DECLARE @sys_usr char(30);  
SET @sys_usr = SYSTEM_USER;  
SELECT 'The current system user is: '+ @sys_usr;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `----------------------------------------------------------`  
  
 `The current system user is: WillisJo`  
  
 `(1 row(s) affected)`  
  
### <a name="b-using-systemuser-with-default-constraints"></a>B. Verwenden von SYSTEM_USER mit DEFAULT-Einschränkungen  
 Im folgenden Beispiel wird eine Tabelle mit `SYSTEM_USER` als `DEFAULT`-Einschränkung für die `SRep_tracking_user`-Spalte erstellt.  
  
```  
USE AdventureWorks2012;  
GO  
CREATE TABLE Sales.Sales_Tracking  
(  
    Territory_id int IDENTITY(2000, 1) NOT NULL,  
    Rep_id  int NOT NULL,  
    Last_sale datetime NOT NULL DEFAULT GETDATE(),  
    SRep_tracking_user varchar(30) NOT NULL DEFAULT SYSTEM_USER  
);  
GO  
INSERT Sales.Sales_Tracking (Rep_id)  
VALUES (151);  
INSERT Sales.Sales_Tracking (Rep_id, Last_sale)  
VALUES (293, '19980515');  
INSERT Sales.Sales_Tracking (Rep_id, Last_sale)  
VALUES (27882, '19980620');  
INSERT Sales.Sales_Tracking (Rep_id)  
VALUES (21392);  
INSERT Sales.Sales_Tracking (Rep_id, Last_sale)  
VALUES (24283, '19981130');  
GO  
```  
  
 Mit der folgenden Abfrage werden alle Informationen aus der `Sales_Tracking`-Tabelle ausgewählt:  
  
```  
SELECT * FROM Sales_Tracking ORDER BY Rep_id;  
GO  
```  
  
 [!INCLUDE[ssResult](../../includes/ssresult-md.md)]  
  
 `Territory_id Rep_id Last_sale            SRep_tracking_user`  
  
 `-----------  ------ -------------------- ------------------`  
  
 `2000         151    Mar 4 1998 10:36AM   ArvinDak`  
  
 `2001         293    May 15 1998 12:00AM  ArvinDak`  
  
 `2003         21392  Mar 4 1998 10:36AM   ArvinDak`  
  
 `2004         24283  Nov 3 1998 12:00AM   ArvinDak`  
  
 `2002         27882  Jun 20 1998 12:00AM  ArvinDak`  
  
 `(5 row(s) affected)`  
  
## <a name="examples-includesssdwfullincludessssdwfull-mdmd-and-includesspdwincludessspdw-mdmd"></a>Beispiele: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] und[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="c-using-systemuser-to-return-the-current-system-user-name"></a>"C:" Verwenden von SYSTEM_USER zur Rückgabe des aktuellen System-Benutzernamens  
 Das folgende Beispiel gibt den aktuellen Wert der `SYSTEM_USER`.  
  
```  
SELECT SYSTEM_USER;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ALTER TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-table-transact-sql.md)   
 [CREATE TABLE &#40;Transact-SQL&#41;](../../t-sql/statements/create-table-transact-sql.md)   
 [CURRENT_TIMESTAMP &#40; Transact-SQL &#41;](../../t-sql/functions/current-timestamp-transact-sql.md)   
 [CURRENT_USER &#40; Transact-SQL &#41;](../../t-sql/functions/current-user-transact-sql.md)   
 [SESSION_USER &#40; Transact-SQL &#41;](../../t-sql/functions/session-user-transact-sql.md)   
 [Systemfunktionen &#40;Transact-SQL&#41;](../../relational-databases/system-functions/system-functions-for-transact-sql.md)   
 [Benutzer &#40; Transact-SQL &#41;](../../t-sql/functions/user-transact-sql.md)  
  
  

