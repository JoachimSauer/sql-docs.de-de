---
title: "RsInternalError – Reporting Services-Fehler | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- reporting-services-sharepoint
- reporting-services-native
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
caps.latest.revision: 23
author: guyinacube
ms.author: asaxton
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: 7265597c2376d62b6d3e42c55c8d87e45f6d869e
ms.contentlocale: de-de
ms.lasthandoff: 08/09/2017

---
# <a name="rsinternalerror---reporting-services-error"></a>rsInternalError – Reporting Services-Fehler
    
## <a name="details"></a>Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|rsInternalError|  
|Ereignisquelle|Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings|  
|Komponente|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|Meldungstext|Interner Fehler beim Berichtsserver. Weitere Informationen finden Sie im Fehlerprotokoll.|  
  
## <a name="explanation"></a>Erklärung  
 Dies ist eine generische Fehlermeldung, auf die häufig ein Fehler mit ausführlicher Beschreibung folgt, die weitere Informationen enthält.  
  
 Interne Fehler treten nicht häufig auf. Wenn dieser Fehler ausgegeben wird, finden Sie weitere Informationen in den Ablaufverfolgungsprotokollen des Berichtsservers. Wenn Sie an demselben Computer als lokaler Administrator angemeldet sind, können Sie zusätzlich die Aufrufliste anzeigen, um weitere Informationen zu erhalten.  
  
## <a name="user-action"></a>Benutzeraktion  
 Um die genaue Ursache für diese Meldung zu bestimmen, überprüfen Sie die Berichtsserver-Protokolldateien, die sich am \Microsoft SQL Server\MSRS12 befinden. \<Instancename > \reporting. Weitere Informationen finden Sie unter [Reporting Services-Protokolldateien und Quellen](../../reporting-services/report-server/reporting-services-log-files-and-sources.md).  
  
 Um die Aufrufliste anzuzeigen, klicken Sie mit der rechten Maustaste auf die Seite, auf der der Fehler auftritt, und zeigen Sie auf **Quelle anzeigen**. Um die Aufrufliste anzuzeigen, sind Administratorberechtigungen für den gleichen Computer erforderlich, auf dem der Fehler aufgetreten ist.  
  
 Wenn keine weiteren Informationen verfügbar sind, versuchen Sie erneut, die Anforderung durchzuführen.  
  
## <a name="internal-only"></a>Nur intern  
  
## <a name="see-also"></a>Siehe auch  
 [Starten Sie und beenden Sie des Berichtsserver-Diensts](../../reporting-services/report-server/start-and-stop-the-report-server-service.md)  
  
  