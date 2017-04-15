---
title: "Analysis Services-Verbindungstyp f&#252;r DMX (SSRS) | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Parameter [Reporting Services], DMX"
  - "Data Mining-Vorhersage [Reporting Services]"
  - "Abfrageansicht [Reporting Services]"
  - "DMX [Reporting Services]"
  - "Entwurfsansicht [Reporting Services]"
  - "Data Mining [Reporting Services]"
  - "Übergeben von Parametern [Reporting Services]"
ms.assetid: 2de825e9-6d8a-4128-add0-da15dc6cea3e
caps.latest.revision: 64
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 64
---
# Analysis Services-Verbindungstyp f&#252;r DMX (SSRS)
  Wenn Sie ein Dataset mithilfe einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenquelle erstellen, wird vom Berichts-Designer standardmäßig der MDX-Abfrage-Designer (Multidimensional Expressions) angezeigt, sobald ein gültiger Cube erkannt wird. Falls kein Cube erkannt wird, jedoch ein Data Mining-Modell verfügbar ist, zeigt der Berichts-Designer den DMX-Abfrage-Designer (Data Mining-Erweiterungen) an. Wenn Sie zwischen den MDX- und DMX-Designern wechseln möchten, verwenden Sie die Symbolleisten-Schaltfläche **DMX-Befehlstyp** (![Ändern der Anzeige der DMX-Abfragesprache](../../reporting-services/report-data/media/rsqdicon-commandtypedmx.png "Ändern der Anzeige der DMX-Abfragesprache")). Mithilfe des DMX-Abfrage-Designers können Sie interaktiv eine DMX-Abfrage erstellen, die grafische Elemente verwendet. Damit der DMX-Abfrage-Designer verwendet werden kann, muss die angegebene Datenquelle bereits über ein Data Mining-Modell verfügen, das die Daten bereitstellt. Die Abfrageergebnisse werden für die Verwendung im Bericht in ein vereinfachtes Rowset konvertiert.  
  
> [!NOTE]  
>  Vor dem Entwerfen Ihres Berichts müssen Sie Ihr Modell trainieren. Weitere Informationen finden Sie unter [Data Mining-Projektmappen](../../analysis-services/data-mining/data-mining-solutions.md).  
  
## Entwurfsmodus  
 Der DMX-Abfrage-Designer wird im Entwurfsmodus geöffnet. Der Entwurfsmodus umfasst eine grafische Entwurfsoberfläche, die zum Auswählen eines einzelnen Data Mining-Modells und einer Eingabetabelle verwendet wird, und ein Raster zum Angeben der Vorhersageabfrage. Im DMX-Abfrage-Designer gibt es zwei weitere Modi: den Abfragemodus und den Ergebnismodus. Im Abfragemodus wird das Raster aus dem Entwurfsmodus durch einen Abfragebereich ersetzt, den Sie für die Eingabe von DMX-Abfragen verwenden können. Im Ergebnismodus wird das von der Abfrage zurückgegebene Resultset in einem Datenraster angezeigt.  
  
 Wenn Sie die Modi für den DMX-Abfrage-Designer ändern möchten, klicken Sie mit der rechten Maustaste auf die Abfrageentwurfsoberfläche, und wählen Sie **Entwurf**, **Abfrage** oder **Ergebnis** aus. Weitere Informationen finden Sie unter [Benutzeroberfläche des DMX-Abfrage-Designers für Analysis Services](../../reporting-services/report-data/analysis-services-dmx-query-designer-user-interface.md) und [Abrufen von Daten aus einem Data Mining-Modell &#40;DMX&#41; &#40;SSRS&#41;](../../reporting-services/report-data/retrieve-data-from-a-data-mining-model-dmx-ssrs.md).  
  
## Entwerfen einer Vorhersageabfrage  
 Der Bereich Abfrageentwurf im Entwurfsmodus enthält zwei Fenster: **Miningmodell** und **Eingabetabelle(n) auswählen**. Verwenden Sie das Fenster **Miningmodell** , um das für die Abfrage zu verwendende Miningmodell auszuwählen. Verwenden Sie das Fenster **Eingabetabelle(n) auswählen** , um die Tabelle auszuwählen, auf der Sie Ihre Vorhersagen basieren möchten. Wenn Sie anstelle einer Eingabetabelle eine SINGLETON-Abfrage verwenden möchten, klicken Sie mit der rechten Maustaste in den Bereich Abfrageentwurf, und wählen Sie **SINGLETON-Abfrage** aus. Das Fenster **Eingabetabelle(n) auswählen** wird durch das Fenster **SINGLETON-Abfrageeingabe** ersetzt.  
  
 Ziehen Sie im Entwurfsmodus die Felder aus den Fenstern **Miningmodell** und **Eingabetabelle(n) auswählen** in die **Feld** -Spalte des Rasterbereichs. Sie können bei Bedarf die verbleibenden Spalten ausfüllen, um einen Alias anzugeben, um das Feld in den Ergebnissen anzuzeigen, um Felder zusammen zu gruppieren und um einen Operator einzugeben, mit dem der Feldwert auf bestimmte Kriterien oder ein Argument begrenzt wird. Wenn Sie sich im Abfragemodus befinden, erstellen Sie die DMX-Abfrage, indem Sie Felder in den Bereich Abfrage ziehen.  
  
## Verwenden von Parametern  
 Sie können Berichtsparameter an einen DMX-Abfrageparameter übergeben. Hierzu müssen Sie Ihrer DMX-Abfrage einen Parameter hinzufügen, die Abfrageparameter im Dialogfeld **Abfrageparameter** definieren und dann die zugeordneten Berichtsparameter ändern. Wenn Sie einen Abfrageparameter definieren möchten, klicken Sie auf der Symbolleiste auf die Schaltfläche **Abfrageparameter** (![Dialogfeld für Abfrageparameter (Symbol)](../../reporting-services/report-data/media/iconqueryparameter.png "Dialogfeld für Abfrageparameter (Symbol)")). Eine Anleitung zum Definieren von Parametern in einer DMX-Abfrage finden Sie unter [Definieren von Parametern im MDX-Abfrage-Designer für Analysis Services &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-data/define parameters in the mdx query designer for analysis services.md).  
  
 Weitere Informationen zum Verwalten der Beziehung zwischen Berichtsparametern und Abfrageparametern finden Sie unter [Zuordnen eines Abfrageparameters zu einem Berichtsparameter &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-data/associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs.md). Weitere Informationen zu Parametern finden Sie unter [Berichtsparameter &#40;Berichts-Generator und Berichts-Designer&#41;](../../reporting-services/report-design/report-parameters-report-builder-and-report-designer.md).  
  
## Siehe auch  
 [Data Mining-Projektmappen](../../analysis-services/data-mining/data-mining-solutions.md)   
 [Abfrageentwurfstools &#40;SSRS&#41;](../../reporting-services/report-data/query-design-tools-ssrs.md)   
 [Datenverbindungen, Datenquellen und Verbindungszeichenfolgen &#40;Berichts-Generator und SSRS&#41;](../../reporting-services/report-data/data-connections-data-sources-and-connection-strings-report-builder-and-ssrs.md)  
  
  