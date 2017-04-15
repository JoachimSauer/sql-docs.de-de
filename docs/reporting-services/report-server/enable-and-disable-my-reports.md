---
title: "Aktivieren und Deaktivieren von &quot;Meine Berichte&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "reporting-services-sharepoint"
  - "reporting-services-native"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Deaktivierter Ordner "Meine Berichte""
  - "Ordner [Reporting Services], „Meine Berichte“"
  - "Aktivierter Ordner "Meine Berichte""
  - "Meine Berichte (Ordner) [Reporting Services]"
  - "Deaktivieren des Ordners Meine Berichte"
ms.assetid: 16c76e82-9fd4-417c-9ed3-a7d5bcd1dba2
caps.latest.revision: 37
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 37
---
# Aktivieren und Deaktivieren von &quot;Meine Berichte&quot;
  Die Funktion Meine Berichte ordnet persönlichen Speicherbereich in der Berichtsserver-Datenbank zu, damit Benutzer ihre eigenen Berichte in einem privaten Ordner speichern können. Als Berichtsserveradministrator können Sie diese Funktion aktivieren bzw. deaktivieren oder dessen Funktionsweise ändern, indem Sie die Sicherheitseinstellungen bearbeiten, die steuern, welche Funktionen die Benutzer mit diesem Arbeitsbereich ausführen können.  
  
 Standardmäßig ist die Funktion Meine Berichte deaktiviert. Diese Funktion kann für alle Benutzer aktiviert oder deaktiviert werden. Es ist jedoch nicht möglich, dieses Funktion nur für bestimmte Benutzer zu aktivieren. Die meisten Benutzer und Organisationen finden diese Funktion hilfreich. Entscheiden Sie anhand der weiter unten in diesem Thema beschriebenen Vor- und Nachteile, ob es für Ihre Organisation geeignet ist.  
  
## Aktivieren und Deaktivieren von Meine Berichte  
 Um Meine Berichte mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]zu aktivieren, stellen Sie eine Verbindung zur Berichtsserverinstanz her, und öffnen Sie die Seite **Servereigenschaften** . Aktivieren Sie dann auf der Registerkarte **Allgemein** Registerkarte die Option **Für jeden Benutzer den Ordner "Meine Berichte" aktivieren** .  
  
 Von der für Meine Berichte verwendeten Rollendefinition hängt es ab, welche Aktionen im Arbeitsbereich Meine Berichte unterstützt werden. Wenn z. B. Verknüpfte Berichte erstellen nicht in der Rolle Meine Berichte enthalten ist, können die Benutzer keine verknüpften Berichte in den Ordnern Meine Berichte erstellen. Weitere Informationen finden Sie unter [Sichern von Meine Berichte](../../reporting-services/security/secure-my-reports.md).  
  
 Zum Deaktivieren von Meine Berichte deaktivieren Sie **Für jeden Benutzer den Ordner 'Meine Berichte' aktivieren**. Dadurch ist der Ordner Meine Berichte für Benutzer überhaupt nicht mehr sichtbar. Die Ordner, die Speicherbereich bereitstellen (d. h. die Unterordner in Benutzerordner), müssen nach der Deaktivierung dieses Funktionen manuell gelöscht werden.  
  
### Wenn Meine Berichte aktiviert ist  
 Wenn diese Funktion aktiviert ist, wird der Ordner Meine Berichte unterhalb des Stammordners Home angezeigt. Neben dem Ordner Meine Berichte ist für Berichtsserveradministratoren außerdem der Ordner Benutzerordner sichtbar, der einen Unterordner für jeden Benutzer enthält.  
  
 Bei aktivierter Funktion können Benutzerordner und dessen Unterordner nicht gelöscht werden. Außerdem wird der Name "Meine Berichte" zu einem reservierten Namen für Unterordner des Stammknotens (Home).  
  
 Wenn Sie Meine Berichte wieder aktivieren, erstellt der Berichtsserver einen neuen Ordner Benutzerordner, falls dieser Ordner noch nicht vorhanden sein sollte. Falls Benutzerordner bereits vorhanden ist, fügt der Berichtsserver neue Unterordner hinzu, wenn sich Benutzer bei ihren Ordnern Meine Berichte anmelden.  
  
### Wenn Meine Berichte deaktiviert ist  
 Wenn diese Funktion deaktiviert ist, wird die Reservierung des Namens "Meine Berichte" aufgehoben. Die Benutzer können dann einen persönlichen Unterordner Meine Berichte im Ordner Home erstellen. Darüber hinaus ist eine Umleitung von Meine Berichte zu benutzerspezifischen Unterordnern von Meine Berichte nicht mehr ausgeführt. Schließlich sind alle Berichtslinks, die einen benutzerspezifischen Ordner Meine Berichte in der URL-Adresse enthalten, nicht mehr funktionsfähig.  
  
## Wählen der Verwendung von Meine Berichte  
 Ob Sie Meine Berichte verwenden, hängt davon ab, ob Sie Serverressourcen zur Unterstützung von Benutzerarbeitsbereichen verwenden möchten. Meine Berichte ist eine leistungsfähige Funktion, mit dem Benutzer Informationsressourcen kontrollieren können, die ihnen das Arbeiten erleichtern. Darüber hinaus handelt es sich dabei für Benutzer um eine Möglichkeit der Verwendung von Berichten, die nicht für den allgemeinen Gebrauch gedacht sind. Einer der überzeugendsten Gründe für die Verwendung von Meine Berichte ist die Tatsache, dass diese Funktion eine sichere, verwaltbare Unterstützung für diejenigen Benutzer ermöglicht, die Berichte erstellen und bearbeiten müssen. Ohne diese Funktion müssten Sie Ordner und Sicherheitsrichtlinien für verschiedene Benutzer auf Ad-hoc-Basis erstellen. Bei der Änderung von Benutzern und Benutzeranforderungen führt diese Vorgehensweise zu einer ständig zunehmenden Zahl von Ordnern und Richtlinien, deren Verwaltung im Laufe der Zeit immer schwieriger wird.  
  
 Beachten Sie, dass beim Aktivieren von Meine Berichte der Berichtsserver einen Ordner Meine Berichte für jeden Benutzer mit einem Domänenkonto erstellt, der auf den Link Meine Berichte klickt, selbst wenn der Benutzer keinen solchen Ordner wünscht oder benötigt. Es gibt keine systematische Methode, um zu ermitteln, welche Ordner verwendet werden. Sie müssen manuell prüfen, ob die Ordner einen Inhalt aufweisen.  
  
## Siehe auch  
 [Sichern von Meine Berichte](../../reporting-services/security/secure-my-reports.md)   
 [Verwalten von Berichtsserverinhalten &#40;einheitlicher SSRS-Modus&#41;](../../reporting-services/report-server/report-server-content-management-ssrs-native-mode.md)  
  
  