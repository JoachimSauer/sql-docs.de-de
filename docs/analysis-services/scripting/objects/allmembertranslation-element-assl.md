---
title: AllMemberTranslation-Element (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/03/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- AllMemberTranslation Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- AllMemberTranslation
helpviewer_keywords:
- AllMemberTranslation element
ms.assetid: 31ec0c44-8f1d-457c-9e8b-61dd5bc468f7
caps.latest.revision: 35
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 34ac096f28bdeac7cb97b963b4cf073a57b5da99
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="allmembertranslation-element-assl"></a>AllMemberTranslation-Element (ASSL)
  Enthält eine Übersetzung für die Beschriftung des alle-Elements ein [Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) Element.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<AllMemberTranslations>  
   <AllMemberTranslation xsi:type="Translation">...  
   </AllMemberTranslation>  
</AllMemberTranslations>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|[Übersetzung](../../../analysis-services/scripting/objects/translation-element-assl.md)|  
|Standardwert|Keine|  
|Kardinalität|0-n: Optionales Element, das mehr als einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnetes Element|[AllMemberTranslations](../../../analysis-services/scripting/collections/allmembertranslations-element-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das Element, das das übergeordnete Element des entspricht, der **AllMemberTranslations** Auflistung im Objektmodell von Analysis Management Objects (AMO) ist <xref:Microsoft.AnalysisServices.Hierarchy>.  
  
## <a name="see-also"></a>Siehe auch  
 [Translation-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/translation-element-assl.md)   
 [Hierarchy-Element &#40; ASSL &#41;](../../../analysis-services/scripting/objects/hierarchy-element-assl.md)   
 [Objekte &#40; ASSL &#41;](../../../analysis-services/scripting/objects/objects-assl.md)  
  
  