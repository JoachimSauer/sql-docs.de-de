---
title: SkippedLevels-Element (XMLA) | Microsoft Docs
ms.custom: 
ms.date: 03/06/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- SkippedLevels Element
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
f1_keywords:
- http://schemas.microsoft.com/analysisservices/2003/engine#SkippedLevels
- microsoft.xml.analysis.skippedlevels
- urn:schemas-microsoft-com:xml-analysis#SkippedLevels
helpviewer_keywords:
- SkippedLevels element
ms.assetid: 4887b557-0ffc-4f42-b6b9-c98ad1208ca5
caps.latest.revision: 11
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d50b4f548b1eee9a45e996e78610c7aa83b3f65e
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="skippedlevels-element-xmla"></a>SkippedLevels-Element (XMLA)
  Enthält die Anzahl der Ebenen, die von einem Attributelement, das vom übergeordneten [Attribute](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md) -Element dargestellt wird, übersprungen werden.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<Attribute>  
   ...  
   <SkippedLevels>...</SkippedLevels>  
   ...  
</Attribute>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Integer|  
|Standardwert|0|  
|Kardinalität|0-1: Optionales Element, das nur einmal auftreten kann.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[Attribut](../../../analysis-services/xmla/xml-elements-properties/attribute-element-xmla.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Das **SkippedLevels** -Element bestimmt die Anzahl der Ebenen, die von einem Attributelement, das vom übergeordneten **Attribute** -Element definiert wird, übersprungen werden.  
  
## <a name="see-also"></a>Siehe auch  
 [INSERT-Element &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/insert-element-xmla.md)   
 [Update-Element &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-commands/update-element-xmla.md)   
 [Datenbankeigenschaften &#40; XMLA &#41;](../../../analysis-services/xmla/xml-elements-properties/xml-elements-properties.md)  
  
  