---
title: MSSQLSERVER_26014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.suite: sql
ms.technology: supportability
ms.tgt_pltfrm: ''
ms.topic: language-reference
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
caps.latest.revision: 10
author: MashaMSFT
ms.author: mathoma
manager: craigg
ms.openlocfilehash: f94a7c0dcd9536240008b965283ded126c644915
ms.sourcegitcommit: ee661730fb695774b9c483c3dd0a6c314e17ddf8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2018
---
# <a name="mssqlserver26014"></a>MSSQLSERVER_26014
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]
  
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|SQL Server|  
|Ereignis-ID|26014|  
|Ereignisquelle|MSSQLSERVER|  
|Komponente|SQLEngine|  
|Symbolischer Name|SNI_SSL_USER_CERT_FAILURE|  
|Meldungstext|Das vom Benutzer angegebene Zertifikat [Cert Hash(sha1) "%hs"] kann nicht geladen werden. Vom Server wird keine Verbindung akzeptiert. Überprüfen Sie, ob das Zertifikat richtig installiert ist. Lesen Sie "Konfigurieren eines Zertifikats zur Verwendung durch SSL" in der Onlinedokumentation.|  
  
## <a name="explanation"></a>Erklärung  
[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hat versucht, das in der Meldung genannte Zertifikat zu laden, aber bei dem Vorgang ist ein Fehler aufgetreten. Dieses Problem muss behoben werden, bevor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dieses Zertifikat verwenden kann.  
  
Zu den möglichen Ursachen für den Fehler zählen die folgenden:  
  
-   Möglicherweise wurde das Zertifikat verschoben oder gelöscht.  
  
-   Falls sich der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendete Anmeldename geändert hat, verfügt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] möglicherweise nicht über die Berechtigung für den Zugriff auf das Zertifikat.  
  
-   Das Zertifikat ist möglicherweise abgelaufen.  
  
## <a name="user-action"></a>Benutzeraktion  
Stellen Sie sicher, dass das in der Meldung genannte Zertifikat im System vorhanden ist, dass darauf zugegriffen werden kann und dass es für die Verwendung zulässig ist.  
  
