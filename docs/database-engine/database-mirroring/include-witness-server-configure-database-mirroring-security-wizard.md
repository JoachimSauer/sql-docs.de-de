---
title: "Zeugenserver einschließen (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/07/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- dbe-high-availability
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sql13.swb.configdbmsecurwiz.inclwitness.f1
ms.assetid: f04b38a4-f4e2-4d4c-bdac-7cc70e5a5684
caps.latest.revision: 32
author: MikeRayMSFT
ms.author: mikeray
manager: jhubbard
ms.translationtype: HT
ms.sourcegitcommit: 1419847dd47435cef775a2c55c0578ff4406cddc
ms.openlocfilehash: f3af2128d62e851e244509365504c361b596c5e5
ms.contentlocale: de-de
ms.lasthandoff: 08/02/2017

---
# <a name="include-witness-server-configure-database-mirroring-security-wizard"></a>Zeugenserver einschließen (Assistent zum Konfigurieren der Sicherheit für die Datenbankspiegelung)
  Verwenden Sie diese Seite, um festzulegen, ob Sie einen Zeugenserver in diese Sicherheitskonfiguration für die Datenbankspiegelung einschließen möchten.  
  
 **So konfigurieren Sie die Datenbankspiegelung mithilfe von SQL Server Management Studio**  
  
-   [Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung &#40;SQL Server Management Studio&#41;](../../database-engine/database-mirroring/establish-database-mirroring-session-windows-authentication.md)  
  
-   [Starten des Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung &#40;SQL Server Management Studio&#41;](../../database-engine/database-mirroring/start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a>Optionen  
 **ja**  
 Klicken Sie hier, um eine Zeugenserverinstanz in die Sicherheitskonfiguration einzubeziehen. Der Zeuge ist erforderlich für den Modus für hohe Sicherheit mit automatischem Failover, der ein automatisches Failover zur Spiegelserverinstanz unterstützt, wenn die Prinzipalserverinstanz einen Fehler erzeugt.  
  
 **Nein**  
 Klicken Sie hier, um die Sicherheit ohne einen Zeugen zu konfigurieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Datenbankspiegelung &#40;SQL Server&#41;](../../database-engine/database-mirroring/database-mirroring-sql-server.md)   
 [Datenbank-Spiegelungszeuge](../../database-engine/database-mirroring/database-mirroring-witness.md)  
  
  