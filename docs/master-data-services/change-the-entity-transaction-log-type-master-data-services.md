---
title: Ändern des Transaktionsprotokolltyps von Entitäten (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: mds
ms.component: non-specific
ms.reviewer: ''
ms.suite: sql
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 75250b32-3384-43c2-9b5c-1607cc3aa7b3
caps.latest.revision: 10
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: d981976b5a8e73ade7063c73eafb1d7a1b9dcd45
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="change-the-entity-transaction-log-type-master-data-services"></a>Ändern des Transaktionsprotokolltyps von Entitäten (Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  Sie können den Transaktionsprotokolltyp einer Entität in "Attribut", "Element" oder "Keiner" ändern.  
  
|Transaktionsprotokolltyp|Description|  
|--------------------------|-----------------|  
|attribute|Entitätsänderungsprotokolle werden auf Attributebene gespeichert.<br /><br /> Das Transaktionsprotokoll wird gespeichert, da es für [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]verwendet wird.|  
|Member|Entitätsänderungsprotokolle werden auf Zeilenebene gespeichert.<br /><br /> Jede Attributänderung löst eine neue Zeilenrevision aus.<br /><br /> Bei Verwendung des Transaktionsprotokolltyps mit Zeilen wird die Entität als langsam veränderliche Dimension vom Typ 4 gespeichert. Die Abonnementsichten vom Typ 2 und Typ 4 (Verlauf) werden unterstützt. Weitere Informationen finden Sie unter [Abonnementsichtformate &#40;Master Data Services&#41;](../master-data-services/subscription-view-formats-master-data-services.md).<br /><br /> Bietet eine bessere Leistung.|  
|InclusionThresholdSetting|Es werden keine Änderungsprotokolle gespeichert.<br /><br /> Bietet die beste Leistung.|  
  
## <a name="prerequisites"></a>Voraussetzungen  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich der Systemverwaltung verfügen. Weitere Informationen finden Sie unter [Berechtigungen für Funktionsbereiche &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md).  
  
-   Sie müssen ein Modelladministrator sein. Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../master-data-services/administrators-master-data-services.md)zuzugreifen.  
  
-   Die Entität muss vorhanden sein. Weitere Informationen finden Sie unter [Erstellen einer Entität &#40;Master Data Services&#41;](../master-data-services/create-an-entity-master-data-services.md).  
  
 **So ändern Sie den Transaktionsprotokolltyp**  
  
1.  Klicken Sie im Master Data Manager auf **Systemverwaltung**.  
  
2.  Wählen Sie auf der Seite **Modell verwalten** die Zeile für das Modell der Entität aus, die Sie bearbeiten möchten, und klicken Sie anschließend auf **Entitäten**.  
  
3.  Wählen Sie auf der Seite **Entität verwalten** die Zeile der Entität aus, die Sie aktualisieren möchten, und klicken Sie anschließend auf **Bearbeiten**.  
  
4.  Wählen Sie in der Dropdownliste des Transaktionsprotokolltyp aus.  
  
5.  Klicken Sie auf **Speichern**.  
  
  
