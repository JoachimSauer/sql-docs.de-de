---
title: STArea (Geometry-Datentyp) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.reviewer: 
ms.suite: 
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- STArea (geometry Data Type)
- STArea_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- STArea (geometry Data Type)
ms.assetid: a7dd6083-c649-4ac3-885d-1234e0db62f1
caps.latest.revision: 25
author: BYHAM
ms.author: rickbyh
manager: jhubbard
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 5ec0a874d0dc2dd8bb37ce7e04fe71cbea85f860
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="starea-geometry-data-type"></a>STArea (geometry-Datentyp)
[!INCLUDE[tsql-appliesto-ss2012-asdb-xxxx-xxx_md](../../includes/tsql-appliesto-ss2012-asdb-xxxx-xxx-md.md)]

  Gibt die gesamte Oberfläche einer **Geometrie** Instanz.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
.STArea ( )  
```  
  
## <a name="return-types"></a>Rückgabetypen  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Rückgabetyp: **"float"**  
  
 CLR-Rückgabetyp: **SqlDouble**  
  
## <a name="remarks"></a>Hinweise  
 `STArea()`Gibt 0 zurück, wenn eine **Geometrie** -Instanz nur 0- und 1-dimensionale Abbildungen enthält oder wenn sie leer ist. `STArea()`Gibt **NULL** Wenn die **Geometrie** Instanz wurde nicht initialisiert.  
  
## <a name="examples"></a>Beispiele  
  
### <a name="a-computing-the-area-of-a-polygon-instance"></a>A. Berechnen der Fläche einer Polygoninstanz  
 Das folgende Beispiel erstellt eine `Polygon``geometry` -Instanz und die Fläche des Polygons berechnet.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POLYGON((0 0, 3 0, 3 3, 0 3, 0 0),(2 2, 2 1, 1 1, 1 2, 2 2))', 0);  
SELECT @g.STArea();  
```  
  
### <a name="b-computing-the-area-of-a-curvepolygon-instance"></a>B. Berechnen der Fläche einer CurvePolygon-Instanz  
 Im folgenden Beispiel wird die Fläche einer `CurvePolygon`-Instanz berechnet.  
  
 `DECLARE @g geometry;`  
  
 `SET @g = geometry::Parse('CURVEPOLYGON(CIRCULARSTRING(0 2, 2 0, 4 2, 4 2, 0 2))');`  
  
 `SELECT @g.STArea() AS Area;`  
  
## <a name="see-also"></a>Siehe auch  
 [OGC-Methoden für Geometry-Instanzen](../../t-sql/spatial-geometry/ogc-methods-on-geometry-instances.md)  
  
  
