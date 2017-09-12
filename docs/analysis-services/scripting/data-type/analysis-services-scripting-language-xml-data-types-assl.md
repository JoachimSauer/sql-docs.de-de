---
title: Analysis Services Scripting Language-XML-Datentypen (ASSL) | Microsoft Docs
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-server-2016
ms.reviewer: 
ms.suite: 
ms.technology:
- analysis-services
- docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- Analysis Services Scripting Language XML Data Types
apilocation:
- http://schemas.microsoft.com/analysisservices/2003/engine
apitype: Schema
applies_to:
- SQL Server 2016 Preview
helpviewer_keywords:
- ASSL, data types
- Analysis Services Scripting Language, data types
- data types [Analysis Services Scripting Language]
ms.assetid: 8e527916-932e-48ec-9010-f22cd4b721e2
caps.latest.revision: 21
author: Minewiskan
ms.author: owend
manager: erikre
ms.translationtype: MT
ms.sourcegitcommit: 876522142756bca05416a1afff3cf10467f4c7f1
ms.openlocfilehash: 63371810e2a7c41fab2935dfeb94a03b9250385a
ms.contentlocale: de-de
ms.lasthandoff: 09/01/2017

---
# <a name="analysis-services-scripting-language-xml-data-types-assl"></a>Analysis Services Scripting Language-XML-Datentypen (ASSL)
  In diesem Referenzabschnitt finden Sie Syntax- und Nutzungsinformationen für jedes Element, das im ASSL-Schema (Analysis Services Scripting Language) als Typ agiert.  
  
 Obwohl das ASSL-Schema nur XML-Elemente, aus der Sicht eines Entwicklers, enthält die Elemente, die in diesem Abschnitt beschriebenen entsprechen Typen, wie z. B. **binden** und **Berechtigung**, die verwendet werden Definieren Sie die untergeordneten Elemente und Eigenschaften anderer Objekte.  
  
 Typelemente wie Objektelemente sind niemals Blattebenenelemente im ASSL-Schema, sondern besitzen untergeordnete Elemente und Elemente, die Objekteigenschaften entsprechen.  
  
 Wird jedoch ein Type-Element niemals als ein Element in einem Skript angezeigt, die definiert oder beschreibt [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Objekte. Stattdessen als Typ eines anderen Objektelemente mit "Normal" gekennzeichnet werden offenbar die **Typ** Attribut aus dem XML-Schemainstanz-Schema mit **xsi: Type** oder **xs: Type**. Beispiel: `<Assembly xsi:type="ClrAssembly">...</Assembly>`.  
  
 In einigen Fällen wird ein Typ von einem anderen Typ abgeleitet. Z. B. die **CubeBinding** Typ leitet sich von der übergeordneten **binden** Typ.  
  
|Element|Description|  
|-------------|-----------------|  
|[Action-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/action-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der eine Aktion in einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element oder eine [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[AggregationAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der die Zuordnung zwischen einer [Aggregation](../../../analysis-services/scripting/objects/aggregation-element-assl.md) -Element und einem Attribut.|  
|[AggregationDesignAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdesignattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der die Zuordnung zwischen einem Attribut darstellt und ein [AggregationDesignDimension](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md) Element.|  
|[AggregationDesignDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Cubedimension darstellt und ein [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md) Element.|  
|[AggregationDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationdimension-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Dimension darstellt und ein [Aggregation](../../../analysis-services/scripting/objects/aggregation-element-assl.md) Element.|  
|[AggregationInstanceAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationinstanceattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein Attribut, das von einer Aggregationsinstanz verwendet wird, darstellt.|  
|[AggregationInstanceCubeDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationinstancecubedimension-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Cubedimension, die von einer Aggregationsinstanz verwendet wird, darstellt.|  
|[AggregationInstanceMeasure-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/aggregationinstancemeasure-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein Measure, das von einer Aggregationsinstanz verwendet wird, darstellt.|  
|[Assembly-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/assembly-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der darstellt eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Assembly oder einer COM-dynamic Link Library (DLL) zugeordneten eine [Server](../../../analysis-services/scripting/objects/server-element-assl.md) oder [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[AttributeBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/attributebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung für eine [Attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) Element.|  
|[AttributeTranslation-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/attributetranslation-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine zugeordnete Übersetzung darstellt, der eine [Attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) Element|  
|[Binding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der eine abhängige Beziehung zwischen zwei Objekten darstellt, in der die Daten oder Metadaten des einen Objekts von den Daten oder Metadaten eines gebundenen Objekts abhängen.|  
|[ClrAssembly-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der darstellt, der eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Assembly zugeordnet eine [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) oder [Server](../../../analysis-services/scripting/objects/server-element-assl.md) Element|  
|[ClrAssemblyFile-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md)|Definiert einen Grunddatentyp, der eine der Dateien darstellt, aus denen, eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Assembly ([ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) Element).|  
|[ColumnBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/columnbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung einer Spalte in einer Datenquellensicht steht eine [DataItem](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md) Element.|  
|[ComAssembly-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/comassembly-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine COM-Bibliothek zugeordnet darstellt, der eine [Server](../../../analysis-services/scripting/objects/server-element-assl.md) oder [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[CubeAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubeattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der ein Attribut zugeordnet darstellt eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[CubeAttributeBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubeattributebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung eines Attributs in einer Cubedimension zu entweder einer Aktions- oder einer Miningstrukturspalte darstellt.|  
|[CubeBinding-Datentyp &#40; Out-of-Line- &#41; &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element und ein [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) Element.|  
|[CubeDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Dimension und einem Cube darstellt.|  
|[CubeDimensionBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimensionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung darstellt, der eine [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md), [Measure](../../../analysis-services/scripting/objects/measure-element-assl.md), oder [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) Element zu einer Cubedimension.|  
|[CubeDimensionPermission-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md)|Definiert einen Grunddatentyp, der die Berechtigungen einer einzelnen Rolle in einer bestimmten Dimension in einem Cube darstellt.|  
|[CubeHierarchy-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/cubehierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen darstellt, zu einer [Hierarchie](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) Element in eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[DataBlock-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Auflistung von Datenblöcken, die zum Speichern des binären Inhalts darstellt, ein [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) Element.|  
|[DataItem-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md)|Definiert einen Grunddatentyp, der die datenbezogenen Merkmale eines Datenelements darstellt, z. B. eine Spalte oder ein Attribut.|  
|[DataMiningMeasureGroupDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dataminingmeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Beziehung zwischen einer Measuregruppe und einer Data Mining-Dimension darstellt.|  
|[DataSource-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der eine Datenquelle in einem [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[DataSourceViewBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/datasourceviewbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung zwischen einer Datenquellensicht und dem übergeordneten Element darstellt.|  
|[DegenerateMeasureGroupDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/degeneratemeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Beziehung zwischen einer degenerierten Dimension (d. h. einer Faktdimension) und einer Measuregruppe darstellt.|  
|[Dimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimension-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Datenbankdimension darstellt.|  
|[DimensionAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md)|Definiert einen primitiven Datentyp, der ein Attribut in einer Dimension darstellt.|  
|[DimensionBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimensionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung zwischen einer Datenquelle darstellt und einen [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) Element.|  
|[DimensionPermission-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dimensionpermission-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die einer Datenbankdimension zugewiesenen Berechtigungen darstellt.|  
|[DrillThroughAction-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/drillthroughaction-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Drillthrough-Aktion darstellt.|  
|[DSVTableBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/dsvtablebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung zwischen einer Tabelle darstellt und einen [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) Element.|  
|[EventColumn-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/eventcolumn-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Spalte mit Informationen für die aufzuzeichnenden darstellt ein [Ereignis](../../../analysis-services/scripting/objects/event-element-assl.md) -Element als Teil einer [Ablaufverfolgung](../../../analysis-services/scripting/objects/trace-element-assl.md) Element.|  
|[Hierarchy-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/hierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Hierarchie in einer Dimension darstellt.|  
|[ImpersonationInfo-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/impersonationinfo-data-type-assl.md)|Definiert einen Grunddatentyp, der die Informationen darstellt, die zur Identitätsbestimmung eines Benutzers verwendet werden.|  
|[IncrementalProcessingNotification-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/incrementalprocessingnotification-data-type-assl.md)|Definiert einen abgeleiteten Datentyp dar Informationen für die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) Element über eine Abfrage zum Ermitteln des Fortschritts der inkrementellen Verarbeitung ausgeführt.|  
|[InheritedBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/inheritedbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der angibt, die eine [MeasureGroupAttribute](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md) -Element seine Bindungen vom Attribut erbt.|  
|[ManyToManyMeasureGroupDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/manytomanymeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Beziehung zwischen einer m:n-Dimension und einer Measuregruppe darstellt.|  
|[MeasureBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measurebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung einer Measure zum übergeordneten Element darstellt.|  
|[MeasureGroupAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einem Attribut und einer Measuregruppe darstellt.|  
|[MeasureGroupBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung an eine [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) Element.|  
|[MeasureGroupBinding-Datentyp &#40; Out-of-Line- &#41; &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)|Definiert einen Grunddatentyp, der eine Bindung mit einer Measuregruppe darstellt.|  
|[MeasureGroupDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupdimension-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der die Beziehung zwischen einer Dimension und einer Measuregruppe darstellt.|  
|[MeasureGroupDimensionBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregroupdimensionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung zwischen einer Dimension und einer Measuregruppe darstellt.|  
|[MeasureGroupHierarchy-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/measuregrouphierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Hierarchie in einer Measuregruppe darstellt.|  
|[MiningModelColumn-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Spalte in einer [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) Element.|  
|[MiningModelingFlag-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningmodelingflag-data-type-assl.md)|Definiert einen Grunddatentyp, der die verfügbaren Modellierungsflags für eine [ModelingFlag](../../../analysis-services/scripting/objects/modelingflag-element-assl.md) Element.|  
|[MiningStructureColumn-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der Informationen über eine Spalte in einer [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) Element.|  
|[OlapDataSource-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/olapdatasource-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der ein mehrdimensionales darstellt [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) Element.|  
|[PartitionBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/partitionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung an eine [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) Element.|  
|[Permission-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|Definiert einen abstrakten, Grunddatentyp, der Informationen über eine individuelle Berechtigung darstellt.|  
|[PerspectiveAction-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectiveaction-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Aktion in einem [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[PerspectiveAttribute-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectiveattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein Attribut in einer [PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md) Element.|  
|[PerspectiveCalculation-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivecalculation-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Berechnung darstellt und einen [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[PerspectiveDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Dimension in einer Perspektive darstellt.|  
|[PerspectiveHierarchy-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivehierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Hierarchie in einer [PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md) Element.|  
|[PerspectiveKpi-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivekpi-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über einen Key Performance Indicator (KPI) darstellt, in eine [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[PerspectiveMeasure-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivemeasure-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Measure in einem [PerspectiveMeasureGroup](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md) Element.|  
|[PerspectiveMeasureGroup-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen zu einer Measuregruppe in einem [Perspektive](../../../analysis-services/scripting/objects/perspective-element-assl.md) Element.|  
|[ProactiveCachingBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingbinding-data-type-assl.md)|Definiert einen abstrakten abgeleiteten Datentyp, die Informationen darstellt, die die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) Element datenquellenänderungen, das Neuerstellen des Caches erfordern, sowie über den Status des Neuerstellungsprozesses.|  
|[ProactiveCachingIncrementalProcessingBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung an die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) Element über den Status des Neuerstellungsprozesses des Caches.|  
|[ProactiveCachingInheritedBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachinginheritedbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, die Informationen darstellt, die die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element über datenquellenänderungen in Tabellen und Sichten, die über vorhandene datenbindungen, das Neuerstellen des Caches erfordern, identifiziert.|  
|[ProactiveCachingObjectNotificationBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingobjectnotificationbinding-data-type-assl.md)|Definiert einen abstrakten abgeleiteten Datentyp, die Informationen darstellt, die die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element über datenquellenänderungen in angegebenen Tabellen und Sichten oder in Tabellen und Sichten, die über vorhandene datenbindungen, identifiziert die Neuerstellen des Caches erfordern.|  
|[ProactiveCachingQueryBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingquerybinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, die Informationen darstellt, die die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element über datenquellenänderungen in Tabellen und Sichten, die über die Ausführung von angegebenen Abfragen, das Neuerstellen des Caches erfordern, identifiziert.|  
|[ProactiveCachingTablesBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/proactivecachingtablesbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, die Informationen darstellt, die die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element über datenquellenänderungen in angegebenen Tabellen und Sichten, die Neuerstellen des Caches erfordern.|  
|[PushedDataSource-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/pusheddatasource-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Datenquelle darstellt (z. B. ein [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Paket) zum "drücken" von Daten in einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[QueryBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/querybinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Zuordnung von einer [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) Element mit einer [QueryDefinition](../../../analysis-services/scripting/properties/querydefinition-element-assl.md) Element.|  
|[ReferenceMeasureGroupDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/referencemeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Dimension darstellt, die indirekt über eine Zwischendimension mit der Faktentabelle verbunden ist. (Eine Sales-Measuregruppe kann beispielsweise auf eine Geography-Dimension verweisen, die über die Customer-Dimension verbunden ist.)|  
|[RegularMeasureGroupDimension-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/regularmeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine reguläre Beziehung zwischen einer Dimension und einer Measuregruppe darstellt.|  
|[RelationalDataSource-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/relationaldatasource-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der darstellt, der eine [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) Element basierend auf einer relationalen Datenquelle.|  
|[ReportAction-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Aktion darstellt, die einen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Bericht generiert.|  
|[RowBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/rowbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung, auf die Zeilen einer Tabelle in darstellt eine [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) Element.|  
|[ScalarMiningStructureColumn-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der darstellt eine [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md) Element, das Skalare Werte als auch im Gegensatz zu den geschachtelten Tabellen zugeordneten enthält die [TableMiningStructureColumn](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md) Element geschachtelte Tabellen enthält.|  
|[StandardAction-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/standardaction-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine stellt [Aktion](../../../analysis-services/scripting/objects/action-element-assl.md) Element außer einer [DrillThroughAction](../../../analysis-services/scripting/data-type/drillthroughaction-data-type-assl.md) Element oder ein [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) Element.|  
|[TableBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tablebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung mit einer Tabelle darstellt.|  
|[TableMiningStructureColumn-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der darstellt eine [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md) Element, das im Gegensatz zu den skalaren Werten, die zugeordneten geschachtelte Tabellen enthalten die [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md) Element Skalare Werte enthält.|  
|[TabularBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/tabularbinding-data-type-assl.md)|Definiert einen abstrakten abgeleiteten Datentyp, der eine Bindung mit einem Tabellenelement wie einer Tabelle oder einer Cubedimension darstellt.|  
|[TimeAttributeBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/timeattributebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der für generierte Elemente in einer Serverzeitdimension (z. B. die Schlüsselspalten eines Attributs) eine "Platzhalter"-Bindung darstellt.|  
|[TimeBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/timebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung an Zeiträume darstellt.|  
|[Translation-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/translation-data-type-assl.md)|Definiert einen Grunddatentyp, der eine lokalisierte Übersetzung darstellt.|  
|[UserDefinedGroupBinding-Datentyp &#40; ASSL &#41;](../../../analysis-services/scripting/data-type/userdefinedgroupbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine benutzerdefinierte Gruppierung für ein Attribut darstellt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services Scripting Language-XML-Element-Hierarchie &#40; ASSL &#41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  