---
title: GetClientInfo-Methode () | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.suite: sql
ms.technology: connectivity
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: b06a5ced-b760-4c78-b17e-854ce95a1a5c
caps.latest.revision: 16
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: 3aecc8bc674fc1ee236baa71a72e469d989d487c
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="getclientinfo-method-"></a>getClientInfo-Methode ()
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Ruft eine Liste mit dem Namen und dem aktuellen Wert der einzelnen Clientinformationseigenschaften ab, die vom JDBC-Treiber unterstützt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
public java.util.Properties getClientInfo()  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Objekt für Eigenschaften, die den Namen und den aktuellen Wert jeder von den Eigenschaften für Clientinformationen unterstützt, die vom Treiber enthält.  
  
## <a name="exceptions"></a>Ausnahmen  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Hinweise  
 Diese GetClientInfo-Methode wird von der GetClientInfo-Methode in der java.sql.Connection-Schnittstelle angegeben.  
  
 Die [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] unterstützt keine Eigenschaften für Clientinformationen. Daher gibt diese Methode ein leeres Eigenschaftenobjekt zurück.  
  
 Auf ähnliche Weise können Anwendungen die [GetClientInfoProperties](../../../connect/jdbc/reference/getclientinfoproperties-method-sqlserverdatabasemetadata.md) Methode der [SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md) Klasse zum Abrufen einer Liste von den Eigenschaften für Clientinformationen, die der Treiber unterstützt. Die [GetClientInfoProperties](../../../connect/jdbc/reference/getclientinfoproperties-method-sqlserverdatabasemetadata.md) Methode gibt ein leeres Resultset zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [GetClientInfo-Methode &#40;SQLServerConnection&#41;](../../../connect/jdbc/reference/getclientinfo-method-sqlserverconnection.md)   
 [SQLServerConnection-Elemente](../../../connect/jdbc/reference/sqlserverconnection-members.md)   
 [SQLServerConnection-Klasse](../../../connect/jdbc/reference/sqlserverconnection-class.md)  
  
  
