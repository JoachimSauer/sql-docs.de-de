---
title: "Geschäftsregelbedingungen (Master Data Services) | Microsoft Docs"
ms.custom: 
ms.date: 03/01/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- master-data-services
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2e0a8c3-4c2e-407c-856e-68d95ebda9ed
caps.latest.revision: 10
author: sabotta
ms.author: carlasab
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: f3481fcc2bb74eaf93182e6cc58f5a06666e10f4
ms.openlocfilehash: b47b8ae7924ae590156479209b2ae0ba639d07ec
ms.contentlocale: de-de
ms.lasthandoff: 08/02/2017

---
# <a name="business-rule-conditions-master-data-services"></a>Geschäftsregelbedingungen (Master Data Services)
  In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]bestimmen Geschäftsregelbedingungen die Bedingungen, die für eine oder mehrere Aktionen, die ausgeführt werden sollen, den Wert "true" haben müssen.  
  
> [!NOTE]  
>  Bedingungen sind optional. Wenn Sie keine Bedingung angeben, werden immer dann Aktionen ausgeführt, wenn Daten gegen Geschäftsregeln überprüft werden.  
  
## <a name="business-rule-conditions"></a>Geschäftsregelbedingungen  
  
|Bedingungsname|Description|  
|--------------------|-----------------|  
|**Ist gleich**|Das ausgewählte Attribut **ist gleich** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text-, Zahlen-, Datums- und Linkwerte gültig.|  
|**Ist nicht gleich**|Das ausgewählte Attribut **ist nicht gleich** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text-, Zahlen-, Datums- und Linkwerte gültig.|  
|**Ist größer als**|Das ausgewählte Attribut **ist größer als** ein bestimmtes Attribut oder ein bestimmter Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text-, Zahlen- und Datumswerte gültig.|  
|**Ist größer als oder gleich**|Das ausgewählte Attribut **ist größer als oder gleich** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text-, Zahlen- und Datumswerte gültig.|  
|**Ist kleiner als**|Das ausgewählte Attribut **ist kleiner als** ein bestimmtes Attribut oder ein bestimmter Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text-, Zahlen- und Datumswerte gültig.|  
|**Ist kleiner als oder gleich**|Das ausgewählte Attribut **ist kleiner als oder gleich** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text-, Zahlen- und Datumswerte gültig.|  
|**Beginnt mit**|Das ausgewählte Attribut **beginnt mit** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**beginnt nicht mit**|Das ausgewählte Attribut **beginnt nicht mit** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**Endet mit**|Das ausgewählte Attribut **endet mit** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**endet nicht mit**|Das ausgewählte Attribut **endet nicht mit** einem bestimmten Attribut oder Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**Enthält**|Das ausgewählte Attribut **enthält** ein bestimmtes Attribut oder einen bestimmten Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**enthält nicht**|Das ausgewählte Attribut **enthält nicht** ein bestimmtes Attribut oder einen Attributwert bzw. ist leer.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**Enthält das Muster**|Das ausgewählte Attribut **enthält das Muster** eines bestimmten Attributs oder Attributwerts bzw. ist leer. Verwenden Sie reguläre Ausdrücke von .NET Framework, um das Muster anzugeben.<br /><br /> Weitere Informationen zu regulären Ausdrücken finden Sie unter [Sprachelemente für reguläre Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=164401) in der MSDN Library.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**enthält nicht das Muster**|Das ausgewählte Attribut **enthält nicht das Muster** eines bestimmten Attributs oder Attributwerts bzw. ist leer. Verwenden Sie reguläre Ausdrücke von .NET Framework, um das Muster anzugeben.<br /><br /> Weitere Informationen zu regulären Ausdrücken finden Sie unter [Sprachelemente für reguläre Ausdrücke](http://go.microsoft.com/fwlink/?LinkId=164401) in der MSDN Library.<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**Enthält die Teilmenge**|Das ausgewählte Attribut **enthält die Teilmenge** eines bestimmten Attributs oder Attributwerts. Sie müssen die Startposition für die Suche angeben (1 bedeutet z. B., dass die Suche beim ersten Zeichen beginnt).<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**enthält nicht die Teilmenge**|Das ausgewählte Attribut **enthält nicht die Teilmenge** eines bestimmten Attributs oder Attributwerts. Sie müssen die Startposition für die Suche angeben (1 bedeutet z. B., dass die Suche beim ersten Zeichen beginnt).<br /><br /> Diese Bedingung ist für Text- und Linkwerte gültig.|  
|**Wurde geändert**|Das ausgewählte Attribut **wurde geändert** , seit das letzte Mal Geschäftsregeln auf das Element angewendet wurden. Sie müssen die Änderungsgruppe angeben, zu der das Attribut gehört.<br /><br /> Weitere Informationen zu Änderungsnachverfolgungsgruppen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).<br /><br /> Diese Bedingung ist für Text-, Zahlen-, Datums- und Linkwerte gültig.|  
|**wurde nicht geändert**|Das ausgewählte Attribut **wurde nicht geändert** , seit zuletzt Geschäftsregeln auf das Element angewendet wurden. Sie müssen die Änderungsgruppe angeben, zu der das Attribut gehört.<br /><br /> Weitere Informationen zu Änderungsnachverfolgungsgruppen finden Sie unter [Hinzufügen von Attributen zu einer Änderungsnachverfolgungsgruppe &#40;Master Data Services&#41;](../master-data-services/add-attributes-to-a-change-tracking-group-master-data-services.md).<br /><br /> Diese Bedingung ist für Text-, Zahlen-, Datums- und Linkwerte gültig.|  
|**Liegt zwischen**|Das ausgewählte Attribut **liegt zwischen** zwei bestimmten Attributwerten.<br /><br /> Diese Bedingung ist für Text-, Zahlen- und Datumswerte gültig.|  
|**ist nicht zwischen**|Das ausgewählte Attribut **ist nicht zwischen** zwei bestimmten Attributwerten.<br /><br /> Diese Bedingung ist für Text-, Zahlen- und Datumswerte gültig.|  
  
> [!NOTE]  
>  Wenn eine Geschäftsregel eine Bedingung enthält, die zwei Werte vergleicht, und die Regel auf ein Element angewendet wird, wofür beide Werte NULL sind, besteht dieses Element keine Überprüfung.  
  
## <a name="see-also"></a>Siehe auch  
 [Geschäftsregelaktionen &#40; Master Data Services &#41;](../master-data-services/business-rule-actions-master-data-services.md)   
 [Geschäftsregeln &#40; Master Data Services &#41;](../master-data-services/business-rules-master-data-services.md)   
 [Erstellen Sie und veröffentlichen Sie einer Geschäftsregel &#40; Master Data Services &#41;](../master-data-services/create-and-publish-a-business-rule-master-data-services.md)  
  
  