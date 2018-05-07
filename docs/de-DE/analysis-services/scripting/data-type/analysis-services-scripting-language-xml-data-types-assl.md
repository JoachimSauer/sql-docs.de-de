---
title: Analysis Services Scripting Language-XML-Datentypen (ASSL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: analysis-services
ms.prod_service: analysis-services
ms.service: ''
ms.component: ''
ms.reviewer: ''
ms.suite: pro-bi
ms.technology: ''
ms.tgt_pltfrm: ''
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
manager: kfile
ms.openlocfilehash: 96513bae9b5be540e10879b23821cbf853b8066b
ms.sourcegitcommit: 2ddc0bfb3ce2f2b160e3638f1c2c237a898263f4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="analysis-services-scripting-language-xml-data-types-assl"></a>Analysis Services Scripting Language-XML-Datentypen (ASSL)
[!INCLUDE[ssas-appliesto-sqlas](../../../includes/ssas-appliesto-sqlas.md)]
  In diesem Referenzabschnitt finden Sie Syntax- und Nutzungsinformationen für jedes Element, das im ASSL-Schema (Analysis Services Scripting Language) als Typ agiert.  
  
 Obwohl das ASSL-Schema nur XML-Elemente, aus der Sicht eines Entwicklers, enthält die Elemente, die in diesem Abschnitt beschriebenen entsprechen Typen, wie z. B. **binden** und **Berechtigung**, die verwendet werden Definieren Sie die untergeordneten Elemente und Eigenschaften anderer Objekte.  
  
 Typelemente wie Objektelemente sind niemals Blattebenenelemente im ASSL-Schema, sondern besitzen untergeordnete Elemente und Elemente, die Objekteigenschaften entsprechen.  
  
 Wird jedoch ein Type-Element niemals als ein Element in einem Skript angezeigt, die definiert oder beschreibt [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] Objekte. Stattdessen als Typ eines anderen Objektelemente mit "Normal" gekennzeichnet werden offenbar die **Typ** Attribut aus dem XML-Schemainstanz-Schema mit **xsi: Type** oder **xs: Type**. Beispiel: `<Assembly xsi:type="ClrAssembly">...</Assembly>`.  
  
 In einigen Fällen wird ein Typ von einem anderen Typ abgeleitet. Z. B. die **CubeBinding** Typ leitet sich von der übergeordneten **binden** Typ.  
  
|Element|Description|  
|-------------|-----------------|  
|[Action-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/action-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der eine Aktion in einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) -Element oder einem [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) -Element darstellt.|  
|[AggregationAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationattribute-data-type-assl.md)|Definiert den Grunddatentyp, der die Zuordnung zwischen einem [Aggregation](../../../analysis-services/scripting/objects/aggregation-element-assl.md) -Element und einem Attribut darstellt.|  
|[AggregationDesignAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationdesignattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der die Zuordnung zwischen einen Attribut und einem [AggregationDesignDimension](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md) -Element darstellt.|  
|[AggregationDesignDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationdesigndimension-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Cubedimension und einem [AggregationDesign](../../../analysis-services/scripting/objects/aggregationdesign-element-assl.md) -Element darstellt.|  
|[AggregationDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationdimension-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Dimension und einem [Aggregation](../../../analysis-services/scripting/objects/aggregation-element-assl.md) -Element darstellt.|  
|[AggregationInstanceAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationinstanceattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein Attribut, das von einer Aggregationsinstanz verwendet wird, darstellt.|  
|[AggregationInstanceCubeDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationinstancecubedimension-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Cubedimension, die von einer Aggregationsinstanz verwendet wird, darstellt.|  
|[AggregationInstanceMeasure-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/aggregationinstancemeasure-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein Measure, das von einer Aggregationsinstanz verwendet wird, darstellt.|  
|[Assembly-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/assembly-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der darstellt eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Assembly oder einer COM-dynamic Link Library (DLL) zugeordneten eine [Server](../../../analysis-services/scripting/objects/server-element-assl.md) oder [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) Element.|  
|[AttributeBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/attributebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung für ein [Attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) -Element darstellt.|  
|[AttributeTranslation-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/attributetranslation-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Übersetzung darstellt, die einem [Attribut](../../../analysis-services/scripting/objects/attribute-element-assl.md) -Element zugeordnet ist.|  
|[Binding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/binding-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der eine abhängige Beziehung zwischen zwei Objekten darstellt, in der die Daten oder Metadaten des einen Objekts von den Daten oder Metadaten eines gebundenen Objekts abhängen.|  
|[ClrAssembly-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der darstellt, der eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Assembly zugeordnet eine [Datenbank](../../../analysis-services/scripting/objects/database-element-assl.md) oder [Server](../../../analysis-services/scripting/objects/server-element-assl.md) Element|  
|[ClrAssemblyFile-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md)|Definiert einen Grunddatentyp, der eine der Dateien darstellt, aus denen, eine [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Assembly ([ClrAssembly](../../../analysis-services/scripting/data-type/clrassembly-data-type-assl.md) Element).|  
|[ColumnBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/columnbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung einer Spalte in einer Datenquellensicht steht eine [DataItem](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md) Element.|  
|[ComAssembly-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/comassembly-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine COM-Bibliothek darstellt, die einem [Server](../../../analysis-services/scripting/objects/server-element-assl.md) - oder [Database](../../../analysis-services/scripting/objects/database-element-assl.md) -Element zugeordnet ist.|  
|[CubeAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubeattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der ein Attribut zugeordnet darstellt eine [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[CubeAttributeBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubeattributebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung eines Attributs in einer Cubedimension zu entweder einer Aktions- oder einer Miningstrukturspalte darstellt.|  
|[CubeBinding-Datentyp & #40; Out-of-Line- & #41; & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubebinding-data-type-out-of-line-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) -Element und einem [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) -Element darstellt.|  
|[CubeDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubedimension-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einer Dimension und einem Cube darstellt.|  
|[CubeDimensionBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubedimensionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung darstellt, der eine [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md), [Measure](../../../analysis-services/scripting/objects/measure-element-assl.md), oder [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) Element zu einer Cubedimension.|  
|[CubeDimensionPermission-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubedimensionpermission-data-type-assl.md)|Definiert einen Grunddatentyp, der die Berechtigungen einer einzelnen Rolle in einer bestimmten Dimension in einem Cube darstellt.|  
|[CubeHierarchy-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/cubehierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein [Hierarchy](../../../analysis-services/scripting/objects/hierarchy-element-assl.md) -Element in einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) -Element darstellt.|  
|[DataBlock-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/datablock-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Auflistung von Datenblöcken darstellt, die verwendet werden, um binäre Inhalte des [ClrAssemblyFile](../../../analysis-services/scripting/data-type/clrassemblyfile-data-type-assl.md) -Elements zu speichern.|  
|[DataItem-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dataitem-data-type-assl.md)|Definiert einen Grunddatentyp, der die datenbezogenen Merkmale eines Datenelements darstellt, z. B. eine Spalte oder ein Attribut.|  
|[DataMiningMeasureGroupDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dataminingmeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Beziehung zwischen einer Measuregruppe und einer Data Mining-Dimension darstellt.|  
|[DataSource-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/datasource-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der eine Datenquelle in einem [Database](../../../analysis-services/scripting/objects/database-element-assl.md) -Element darstellt.|  
|[DataSourceViewBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/datasourceviewbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung zwischen einer Datenquellensicht und dem übergeordneten Element darstellt.|  
|[DegenerateMeasureGroupDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/degeneratemeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Beziehung zwischen einer degenerierten Dimension (d. h. einer Faktdimension) und einer Measuregruppe darstellt.|  
|[Dimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dimension-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Datenbankdimension darstellt.|  
|[DimensionAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dimensionattribute-data-type-assl.md)|Definiert einen primitiven Datentyp, der ein Attribut in einer Dimension darstellt.|  
|[DimensionBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dimensionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung zwischen einer Datenquelle und einem [Dimension](../../../analysis-services/scripting/objects/dimension-element-assl.md) -Element darstellt.|  
|[DimensionPermission-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dimensionpermission-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die einer Datenbankdimension zugewiesenen Berechtigungen darstellt.|  
|[DrillThroughAction-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/drillthroughaction-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Drillthrough-Aktion darstellt.|  
|[DSVTableBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/dsvtablebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung zwischen einer Tabelle und einem [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) -Element darstellt.|  
|[EventColumn-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/eventcolumn-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Spalte mit Informationen darstellt, die für ein [Event](../../../analysis-services/scripting/objects/event-element-assl.md) -Element als Teil eines [Trace](../../../analysis-services/scripting/objects/trace-element-assl.md) -Elements aufgezeichnet werden.|  
|[Hierarchy-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/hierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Hierarchie in einer Dimension darstellt.|  
|[ImpersonationInfo-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/impersonationinfo-data-type-assl.md)|Definiert einen Grunddatentyp, der die Informationen darstellt, die zur Identitätsbestimmung eines Benutzers verwendet werden.|  
|[IncrementalProcessingNotification-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/incrementalprocessingnotification-data-type-assl.md)|Definiert einen abgeleiteten Datentyp dar Informationen für die [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) Element über eine Abfrage zum Ermitteln des Fortschritts der inkrementellen Verarbeitung ausgeführt.|  
|[InheritedBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/inheritedbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der anzeigt, dass ein [MeasureGroupAttribute](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md) -Element seine Bindungen vom Attribut erbt.|  
|[ManyToManyMeasureGroupDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/manytomanymeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Beziehung zwischen einer m:n-Dimension und einer Measuregruppe darstellt.|  
|[MeasureBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measurebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Bindung einer Measure zum übergeordneten Element darstellt.|  
|[MeasureGroupAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measuregroupattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der die Beziehung zwischen einem Attribut und einer Measuregruppe darstellt.|  
|[MeasureGroupBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung mit einem [MeasureGroup](../../../analysis-services/scripting/objects/measuregroup-element-assl.md) -Element darstellt.|  
|[MeasureGroupBinding-Datentyp & #40; Out-of-Line- & #41; & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measuregroupbinding-data-type-out-of-line-assl.md)|Definiert einen Grunddatentyp, der eine Bindung mit einer Measuregruppe darstellt.|  
|[MeasureGroupDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measuregroupdimension-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der die Beziehung zwischen einer Dimension und einer Measuregruppe darstellt.|  
|[MeasureGroupDimensionBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measuregroupdimensionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung zwischen einer Dimension und einer Measuregruppe darstellt.|  
|[MeasureGroupHierarchy-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/measuregrouphierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Hierarchie in einer Measuregruppe darstellt.|  
|[MiningModelColumn-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/miningmodelcolumn-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Spalte in einem [MiningModel](../../../analysis-services/scripting/objects/miningmodel-element-assl.md) -Element darstellt.|  
|[MiningModelingFlag-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/miningmodelingflag-data-type-assl.md)|Definiert einen Grunddatentyp, der die verfügbaren Modellierungsflags für ein [ModelingFlag](../../../analysis-services/scripting/objects/modelingflag-element-assl.md) -Element darstellt.|  
|[MiningStructureColumn-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md)|Definiert einen abstrakten Grunddatentyp, der Informationen über eine Spalte in einem [MiningStructure](../../../analysis-services/scripting/objects/miningstructure-element-assl.md) -Element darstellt.|  
|[OlapDataSource-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/olapdatasource-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der ein mehrdimensionales [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) -Element darstellt.|  
|[PartitionBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/partitionbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung mit einem [Partition](../../../analysis-services/scripting/objects/partition-element-assl.md) -Element darstellt.|  
|[Permission-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/permission-data-type-assl.md)|Definiert einen abstrakten, Grunddatentyp, der Informationen über eine individuelle Berechtigung darstellt.|  
|[PerspectiveAction-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectiveaction-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Aktion in einem [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) -Element darstellt.|  
|[PerspectiveAttribute-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectiveattribute-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über ein Attribut in einem [PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md) -Element darstellt.|  
|[PerspectiveCalculation-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectivecalculation-data-type-assl.md)|Definiert den Grunddatentyp, der die Beziehung zwischen einer Berechnung und einem [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) -Element darstellt.|  
|[PerspectiveDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Dimension in einer Perspektive darstellt.|  
|[PerspectiveHierarchy-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectivehierarchy-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Hierarchie in einem [PerspectiveDimension](../../../analysis-services/scripting/data-type/perspectivedimension-data-type-assl.md) -Element darstellt.|  
|[PerspectiveKpi-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectivekpi-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Aktion in einen Key Performance Indicator (KPI) in einem [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) -Element darstellt.|  
|[PerspectiveMeasure-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectivemeasure-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Measure in einem [PerspectiveMeasureGroup](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md) -Element darstellt.|  
|[PerspectiveMeasureGroup-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/perspectivemeasuregroup-data-type-assl.md)|Definiert einen Grunddatentyp, der Informationen über eine Measuregruppe in einem [Perspective](../../../analysis-services/scripting/objects/perspective-element-assl.md) -Element darstellt.|  
|[ProactiveCachingBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/proactivecachingbinding-data-type-assl.md)|Definiert einen abstrakten abgeleiteten Datentyp, der Informationen über Datenquellenänderungen, die ein Neuerstellen des Caches erfordern, sowie über den Status des Neuerstellungsprozesses für das [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element darstellt.|  
|[ProactiveCachingIncrementalProcessingBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/proactivecachingincrementalprocessingbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung zum [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element bezüglich des Status des Neuerstellungsprozesses des Caches darstellt.|  
|[ProactiveCachingInheritedBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/proactivecachinginheritedbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der dem [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element gegenüber Informationen über Datenquellenänderungen in Tabellen und Sichten darstellt, die über vorhandene Datenbindungen, die ein Neuerstellen des Caches erfordern, identifiziert werden.|  
|[ProactiveCachingObjectNotificationBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/proactivecachingobjectnotificationbinding-data-type-assl.md)|Definiert einen abstrakten abgeleiteten Datentyp, der dem [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element gegenüber Informationen über Datenquellenänderungen darstellt, entweder in angegebenen Tabellen und Sichten oder in Tabellen und Sichten, die über vorhandene Datenbindungen, die ein Neuerstellen des Caches erfordern, identifiziert werden.|  
|[ProactiveCachingQueryBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/proactivecachingquerybinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der dem [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element gegenüber Informationen über Datenquellenänderungen in Tabellen und Sichten darstellt, die über die Ausführung von angegebenen Abfragen, die ein Neuerstellen des Caches erfordern, identifiziert werden.|  
|[ProactiveCachingTablesBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/proactivecachingtablesbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der dem [ProactiveCaching](../../../analysis-services/scripting/objects/proactivecaching-element-assl.md) -Element gegenüber Informationen über Datenquellenänderungen in angegebenen Tabellen und Sichten darstellt, die über vorhandene Datenbindungen, die ein Neuerstellen des Caches erfordern, identifiziert werden.|  
|[PushedDataSource-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/pusheddatasource-data-type-assl.md)|Definiert einen Grunddatentyp, der eine Datenquelle darstellt (z. B. ein [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] Paket) zum "drücken" von Daten in einem [Cube](../../../analysis-services/scripting/objects/cube-element-assl.md) Element.|  
|[QueryBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/querybinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der die Zuordnung eines [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) -Elements zu einem [QueryDefinition](../../../analysis-services/scripting/properties/querydefinition-element-assl.md) -Element darstellt.|  
|[ReferenceMeasureGroupDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/referencemeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Dimension darstellt, die indirekt über eine Zwischendimension mit der Faktentabelle verbunden ist. (Eine Sales-Measuregruppe kann beispielsweise auf eine Geography-Dimension verweisen, die über die Customer-Dimension verbunden ist.)|  
|[RegularMeasureGroupDimension-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/regularmeasuregroupdimension-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine reguläre Beziehung zwischen einer Dimension und einer Measuregruppe darstellt.|  
|[RelationalDataSource-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/relationaldatasource-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der ein auf einer relationalen Datenquelle basierendes [DataSource](../../../analysis-services/scripting/objects/datasource-element-assl.md) -Element darstellt.|  
|[ReportAction-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Aktion darstellt, die einen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Bericht generiert.|  
|[RowBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/rowbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung zu den Zellen einer Tabelle in einem [DataSourceView](../../../analysis-services/scripting/objects/datasourceview-element-assl.md) -Element darstellt.|  
|[ScalarMiningStructureColumn-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der ein [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md) -Element darstellt, das skalare Werte enthält; dies steht im Gegensatz zu den geschachtelten Tabellen, die dem [TableMiningStructureColumn](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md) -Element zugeordnet sind, das geschachtelte Tabellen enthält.|  
|[StandardAction-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/standardaction-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der ein beliebiges [Action](../../../analysis-services/scripting/objects/action-element-assl.md) -Element darstellt, außer einem [DrillThroughAction](../../../analysis-services/scripting/data-type/drillthroughaction-data-type-assl.md) -Element oder einem [ReportAction](../../../analysis-services/scripting/data-type/reportaction-data-type-assl.md) -Element.|  
|[TableBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/tablebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung mit einer Tabelle darstellt.|  
|[TableMiningStructureColumn-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/tableminingstructurecolumn-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der ein [MiningStructureColumn](../../../analysis-services/scripting/data-type/miningstructurecolumn-data-type-assl.md) -Element darstellt, das geschachtelte Tabellen enthält; dies steht im Gegensatz zu den skalaren Werten, die dem [ScalarMiningStructureColumn](../../../analysis-services/scripting/data-type/scalarminingstructurecolumn-data-type-assl.md) -Element zugeordnet sind, das skalare Werte enthält.|  
|[TabularBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/tabularbinding-data-type-assl.md)|Definiert einen abstrakten abgeleiteten Datentyp, der eine Bindung mit einem Tabellenelement wie einer Tabelle oder einer Cubedimension darstellt.|  
|[TimeAttributeBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/timeattributebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der für generierte Elemente in einer Serverzeitdimension (z. B. die Schlüsselspalten eines Attributs) eine "Platzhalter"-Bindung darstellt.|  
|[TimeBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/timebinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine Bindung an Zeiträume darstellt.|  
|[Translation-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/translation-data-type-assl.md)|Definiert einen Grunddatentyp, der eine lokalisierte Übersetzung darstellt.|  
|[UserDefinedGroupBinding-Datentyp & #40; ASSL & #41;](../../../analysis-services/scripting/data-type/userdefinedgroupbinding-data-type-assl.md)|Definiert einen abgeleiteten Datentyp, der eine benutzerdefinierte Gruppierung für ein Attribut darstellt.|  
  
## <a name="see-also"></a>Siehe auch  
 [Analysis Services Scripting Language-XML-Element-Hierarchie & #40; ASSL & #41;](../../../analysis-services/scripting/analysis-services-scripting-language-xml-element-hierarchy-assl.md)  
  
  