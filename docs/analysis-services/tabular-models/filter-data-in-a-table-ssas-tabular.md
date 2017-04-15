---
title: "Filtern von Daten in einer Tabelle (SSAS – tabellarisch) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "analysis-services"
  - "analysis-services/multidimensional-tabular"
  - "analysis-services/data-mining"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.asvs.bidtoolset.notallitemsshowing.f1"
  - "sql13.asvs.bidtoolset.autofiltermenu.f1"
  - "sql13.asvs.bidtoolset.customfilterdb.f1"
ms.assetid: 3223059d-f525-4835-bf88-ebc195d9dbdc
caps.latest.revision: 13
author: "Minewiskan"
ms.author: "owend"
manager: "erikre"
caps.handback.revision: 13
---
# Filtern von Daten in einer Tabelle (SSAS – tabellarisch)
  Sie können beim Importieren von Daten Filter anwenden, um zu steuern, welche Zeilen in eine Tabelle geladen werden. Nachdem Sie die Daten importiert haben, können Sie keine einzelnen Zeilen löschen. Sie können jedoch benutzerdefinierte Filter anwenden, um zu steuern, wie Zeilen angezeigt werden. Zeilen, die die Filterkriterien nicht erfüllen, werden ausgeblendet. Sie können nach einer oder mehreren Spalten filtern. Filter sind additiv. Das bedeutet, dass jeder zusätzliche Filter auf dem aktuellen Filter basiert und die Teilmenge der Daten weiter reduziert.  
  
> [!NOTE]  
>  Das Filtervorschaufenster schränkt die Anzahl der unterschiedlichen Werte ein, die angezeigt werden. Wenn die Grenze überschritten wird, wird eine Meldung angezeigt.  
  
### So filtern Sie Daten auf Grundlage von Spaltenwerten  
  
1.  Wählen Sie im Modell-Designer eine Tabelle aus, und klicken Sie dann auf den Pfeil in der Kopfzeile der Spalte, nach der Sie filtern möchten.  
  
2.  Führen Sie im Menü AutoFilter einen der folgenden Schritte aus:  
  
    -   Wählen Sie in der Liste der Spaltenwerte mindestens einen Wert aus, nach dem gefiltert werden soll, bzw. heben Sie die Auswahl auf, und klicken Sie auf **OK**.  
  
         Wenn die Anzahl der Werte sehr groß ist, kann es sein, dass einzelne Elemente nicht in der Liste angezeigt werden. Stattdessen wird eine Meldung angezeigt, dass zu viele Elemente zum Anzeigen vorhanden sind.  
  
    -   Klicken Sie je nach Typ der Spalte auf **Zahlenfilter** oder **Textfilter**, und klicken Sie anschließend auf einen der Vergleichsoperatorbefehle (wie **Ist gleich**), oder klicken Sie auf **Benutzerdefinierter Filter**. Erstellen Sie im Dialogfeld **Benutzerdefinierter Filter** den Filter, und klicken Sie dann auf **OK**.  
  
### So löschen Sie einen Filter für eine Spalte  
  
1.  Klicken Sie auf den Pfeil in der Kopfzeile der Spalte, für die Sie den Filter löschen möchten.  
  
2.  Klicken Sie auf **Filter von \<Spaltenname> löschen**.  
  
### So löschen Sie alle Filter für eine Tabelle  
  
1.  Wählen Sie im Modell-Designer die Tabelle aus, für die Sie die Filter löschen möchten.  
  
2.  Klicken Sie auf das Menü **Spalte** und dann auf **Alle Filter löschen**.  
  
## Siehe auch  
 [Filtern und Sortieren von Daten &#40;SSAS – tabellarisch&#41;](../Topic/Filter%20and%20Sort%20Data%20\(SSAS%20Tabular\).md)   
 [Perspektiven &#40;SSAS – tabellarisch&#41;](../../analysis-services/tabular-models/perspectives-ssas-tabular.md)   
 [Rollen &#40;SSAS – tabellarisch&#41;](../../analysis-services/tabular-models/roles-ssas-tabular.md)  
  
  