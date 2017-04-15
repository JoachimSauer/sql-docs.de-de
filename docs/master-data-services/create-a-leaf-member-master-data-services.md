---
title: "Erstellen eines Blattelements (Master Data Services) | Microsoft Docs"
ms.custom: 
  - "SQL2016_New_Updated"
ms.date: "03/17/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "master-data-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Blattelemente [Master Data Services], erstellen"
  - "Erstellen von Blattelementen [Master Data Services]"
  - "Elemente [Master Data Services], Erstellen von Blattelementen"
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
caps.latest.revision: 14
author: "sabotta"
ms.author: "carlasab"
manager: "jhubbard"
caps.handback.revision: 14
---
# Erstellen eines Blattelements (Master Data Services)
  In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] erstellen Sie ein Blattelement, wenn Sie dem System Masterdaten hinzufügen möchten. Wenn Sie Daten in einer Massenoperation hinzufügen möchten, verwenden Sie stattdessen Stagingtabellen. Weitere Informationen finden Sie unter [Importieren von Daten aus Tabellen &#40;Master Data Services&#41;](../master-data-services/import-data-from-tables-master-data-services.md).  
  
 Sie können zum Importieren von Daten auch [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] verwenden.  
  
## Erforderliche Komponenten  
 So führen Sie diese Prozedur aus  
  
-   Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.  
  
-   Sie müssen mindestens die Berechtigung **Erstellen** oder **Aktualisieren** für das Blattmodellobjekt für die Entität besitzen, der Sie ein Element hinzufügen. Die Berechtigung "Erstellen" ermöglicht die Erstellung eines Elements sowie die Bearbeitung des Attributs "Code". Die Berechtigung "Aktualisieren" ermöglicht auch die Aktualisierung anderer Attribute.  
  
     Weitere Informationen finden Sie unter [Sicherheit &#40;Master Data Services&#41;](../master-data-services/security-master-data-services.md).  
  
### So erstellen Sie ein Blattelement  
  
1.  Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.  
  
2.  Wenn Sie Benutzer sind, wählen Sie eine geöffnete Version aus der Liste **Version** aus. Wenn Sie Administrator sind, wählen Sie eine Version mit dem Status „Geöffnet“ oder „Gesperrt“ aus der Liste **Version** aus.  
  
3.  Klicken Sie auf **Explorer**.  
  
4.  Zeigen Sie auf der Menüleiste auf **Entitäten**, und klicken Sie auf den Namen der Entität, der Sie ein Element hinzufügen möchten.  
  
5.  Klicken Sie auf **Element hinzufügen**.  
  
6.  Vervollständigen Sie die Felder im Bereich **Details**.  
  
     Bei einem domänenbasierten Attribut, auf das ein Filter angewendet wird, wird die Liste der Attributwerte durch das übergeordnete Filterattribut eingeschränkt.  
  
     Weitere Informationen zu übergeordneten Filterattributen und domänenbasierten Attributen finden Sie unter [Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;](../master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
7.  Optional. Geben Sie im Feld **Anmerkungen** einen Kommentar dazu ein, warum das Element hinzugefügt wurde. Alle Benutzer, die Zugriff auf das Element haben, können die Anmerkung anzeigen.  
  
8.  Klicken Sie auf **OK**.  
  
## Siehe auch  
 [Erstellen eines konsolidierten Elements &#40;Master Data Services&#41;](../master-data-services/create-a-consolidated-member-master-data-services.md)   
 [Elemente &#40;Master Data Services&#41;](../master-data-services/members-master-data-services.md)  
  
  