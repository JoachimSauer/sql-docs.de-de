---
title: ContextualNameRule-Element (XML) | Microsoft Docs
ms.custom: 
ms.date: 03/04/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
applies_to:
- SQL Server 2016 Preview
ms.assetid: eb567ef8-f412-4d34-837a-75e53b88b3ce
caps.latest.revision: 6
author: jeannt
ms.author: jeannt
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: d5860c69f618cb9c1cb131bf2da377bad405c09b
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="contextualnamerule-element-xml"></a>ContextualNameRule-Element (XML)
  Bietet einen Hinweis zur besten Möglichkeit, einen zusammengesetzten Namen für das Attribut zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
  
<RelationshipEndVisualizationProperties>  
   ...  
   <ContextualNameRule>...</ContextualNameRule>  
   ...  
</RelationshipEndVisualizationProperties>  
```  
  
## <a name="element-characteristics"></a>Elementmerkmale  
  
|Merkmal|Beschreibung|  
|--------------------|-----------------|  
|Datentyp und -länge|Zeichenfolge (Enumeration)|  
|Standardwert|-1|  
|Kardinalität|0-1: Optionales Element, das nur einmal auftritt.|  
  
## <a name="element-relationships"></a>Elementbeziehungen  
  
|Beziehung|Element|  
|------------------|-------------|  
|Übergeordnete Elemente|[RelationshipEndVisualizationProperties](../../../analysis-services/scripting/data-type/relationshipendvisualizationproperties-data-type-assl.md)|  
|Untergeordnete Elemente|Keine|  
  
## <a name="remarks"></a>Hinweise  
 Bietet einen Hinweis zu Clientanwendungen bezüglich der Erstellung von eindeutigen Namen für dieses Attribut.  
  
 Der Wert des **ContextualNameRule** -Elements ist auf eine der in der folgenden Tabelle aufgelisteten Zeichenfolgen beschränkt.  
  
|Wert|Description|  
|-----------|-----------------|  
|*Keine*|Verwendet den Namen des Attributs.|  
|*Kontext*|Verwendet den Namen der eingehenden Beziehung.|  
|*Merge*|Gemäß den Regeln der Anwendungssprache werden der Name der eingehenden Beziehung und der Attributname verkettet.|  
  
  