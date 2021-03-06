---
title: LastPeriods (MDX) | Microsoft Docs
ms.date: 05/30/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: 102382bf2acc2300d5862b48c5341c218e785275
ms.sourcegitcommit: 808d23a654ef03ea16db1aa23edab496b73e5072
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2018
ms.locfileid: "34578982"
---
# <a name="lastperiods-mdx"></a>LastPeriods (MDX)
[!INCLUDE[ssas-appliesto-sqlas](../includes/ssas-appliesto-sqlas.md)]

  Gibt eine Menge von Elementen bis zu einem angegebenen Element, einschließlich des Elements, zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
LastPeriods(Index [ ,Member_Expression ] )  
```  
  
## <a name="arguments"></a>Argumente  
 *Index*  
 Ein gültiger numerischer Ausdruck, der eine Anzahl von Zeiträumen angibt.  
  
 *Member_Expression*  
 Ein gültiger MDX-Ausdruck (Multidimensional Expressions), der ein Element zurückgibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die angegebene Anzahl von Zeiträumen positiv ist, wird die **LastPeriods** Funktion gibt eine Menge von Elementen, die mit dem Element beginnen, die zurückliegen *Index* -1 aus dem angegebenen Elementausdruck befindet und endet mit dem angegebenen Element. Die Anzahl der von der Funktion zurückgegebenen Elemente entspricht *Index*.  
  
 Wenn die angegebene Anzahl von Zeiträumen negativ ist, wird die **LastPeriods** Funktion gibt eine Menge von Elementen, die mit dem angegebenen Element beginnt und endet mit dem Element, das führt (- *Index* - 1) aus den angegebenen Member auf. Die Anzahl der von der Funktion zurückgegebenen Elemente gleich den absoluten Wert des *Index*.  
  
 Wenn die angegebene Anzahl von Zeiträumen NULL ist, ist die **LastPeriods** Funktion die leere Menge zurück. Dies ist im Gegensatz zu den **Lag** -Funktion, die das angegebene Element zurück, wenn 0 angegeben wird.  
  
 Wenn ein Element nicht angegeben wird, die **LastPeriods** Funktion verwendet **Time.CurrentMember**. Wenn keine Dimension als Time-Dimension markiert ist, wird die Funktion fehlerfrei analysiert und ausgeführt, erzeugt aber bei der Clientanwendung einen Zellenfehler.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird der Standardmeasurewert für das zweite, dritte und vierte Geschäftsquartal des Geschäftsjahres 2002 zurückgegeben.  
  
```  
SELECT LastPeriods(3,[Date].[Fiscal].[Fiscal Quarter].[Q4 FY 2002]) ON 0  
FROM [Adventure Works]  
```  
  
> [!NOTE]  
>  Diese Beispiel kann auch mithilfe des Doppelpunkt-Operators (:) formuliert werden:  
>   
>  `[Date].[Fiscal].[Fiscal Quarter].[Q4 FY 2002]: [Date].[Fiscal].[Fiscal Quarter].[Q2 FY 2002]`  
  
 Im folgenden Beispiel wird der Standardmeasurewert für das erste Quartal im Geschäftsjahr 2002 zurückgegeben. Obwohl für die Anzahl der Zeiträume 3 angegeben wurde, kann nur der Wert für einen Zeitraum zurückgegeben werden, da es keine Zeiträume gibt, die vor dem angegebenen im Geschäftsjahr liegen.  
  
```  
SELECT LastPeriods  
   (3,[Date].[Fiscal].[Fiscal Quarter].[Q1 FY 2002]  
   ) ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Siehe auch  
 [MDX-Funktionsreferenz &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
