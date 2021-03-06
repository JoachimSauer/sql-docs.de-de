---
title: Hinzufügen oder Entfernen von Rändern aus einem Diagramm (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/03/2017
ms.prod: reporting-services
ms.prod_service: reporting-services-sharepoint, reporting-services-native
ms.component: report-design
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 91c43f58-5771-4d33-a54d-0e802d2f5cba
caps.latest.revision: 8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a42d78cca3bc4835771c2e9fcf30a184232aeb38
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="add-or-remove-margins-from-a-chart-report-builder-and-ssrs"></a>Hinzufügen oder Entfernen von Rändern aus einem Diagramm (Berichts-Generator und SSRS)
Bei Säulen- und Punktdiagrammen in paginierten [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Berichten fügt das Diagramm an den Enden der X-Achse automatisch Seitenränder hinzu. Bei Balkendiagrammen werden an den Enden der x-Achse automatisch Seitenränder hinzugefügt. Bei allen anderen Diagrammtypen fügt das Diagramm keine Seitenränder hinzu. Die Größe der Seitenränder kann nicht geändert werden.  
  
 Dieses Thema gilt nicht für Kreis-, Ring-, Trichter- oder Pyramidendiagramme.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="to-enable-or-disable-side-margins"></a>So aktivieren oder deaktivieren Sie Seitenränder  
  
1.  Klicken Sie mit der rechten Maustaste auf die Achse, und wählen Sie **Achseneigenschaften**aus. Das Dialogfeld **Eigenschaften für vertikale Achsen** oder **Eigenschaften für horizontale Achsen** wird angezeigt.  
  
2.  Legen Sie auf der Seite **Achsenoptionen** die Eigenschaft **Seitenränder** fest:  
  
    -   **Automatisch:** Das Diagramm bestimmt basierend auf dem Diagrammtyp, ob ein Seitenrand hinzugefügt wird.  
  
    -   **Deaktiviert:** Balken-, Säulen- und Punktdiagramme haben keine Seitenränder.  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen finden Sie unter  
 [Formatieren von Achsenbezeichnungen in einem Diagramm &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/formatting-axis-labels-on-a-chart-report-builder-and-ssrs.md)   
 [Achseneigenschaften (Dialogfeld), Achsenoptionen (Berichts-Generator und SSRS)](http://msdn.microsoft.com/library/b276e210-7a12-48ae-971b-7dabae51df11)   
 [Angeben eines Achsenintervalls (Berichts-Generator und SSRS)](../../reporting-services/report-design/specify-an-axis-interval-report-builder-and-ssrs.md)   
 [Formatieren von Achsenbezeichnungen als Datumsangabe oder Währung (Berichts-Generator und SSRS)](../../reporting-services/report-design/format-axis-labels-as-dates-or-currencies-report-builder-and-ssrs.md)   
 [Diagramme &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-design/charts-report-builder-and-ssrs.md)  
  
  
