---
title: "Abrufen von Informationen zu Ereignisbenachrichtigungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/06/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "database-engine"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ereignisbenachrichtigungen [SQL Server], Metadaten"
  - "Statusinformationen [SQL Server], Ereignisbenachrichtigungen"
  - "Metadaten [SQL Server], Ereignisbenachrichtigungen"
ms.assetid: 8bc10867-66d6-4f57-ac32-a6c29f3327cd
caps.latest.revision: 22
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 22
---
# Abrufen von Informationen zu Ereignisbenachrichtigungen
  Zum Abfragen von Metadaten zu Ereignisbenachrichtigungen stehen die folgenden Katalogsichten zur Verfügung.  
  
 **So rufen Sie Informationen zu Ereignisbenachrichtigungen auf der Nichtserverebene ab**  
  
-   [sys.event_notifications &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-event-notifications-transact-sql.md)  
  
> [!NOTE]  
>  Um in **sys.event_notifications** Metadaten zu Ereignisbenachrichtigungen anzeigen zu können, die auf der Datenbankebene erstellt wurden, müssen folgende Voraussetzungen erfüllt sein: Sie müssen über CONTROL-, ALTER-, TAKE OWNERSHIP- oder VIEW DEFINITION-Berechtigungen für die Datenbank verfügen, Sie müssen der Besitzer der Ereignisbenachrichtigung sein oder über die ALTER ANY DATABASE EVENT NOTIFICATION-Berechtigung verfügen. Für Ereignisbenachrichtigungen, die für eine bestimmte Warteschlange erstellt wurden, müssen mindestens die folgenden Voraussetzungen erfüllt sein: Sie müssen über CONTROL-, ALTER-, TAKE OWNERSHIP- oder VIEW DEFINITION-Berechtigungen für das Objekt verfügen, Sie müssen der Besitzer der Ereignisbenachrichtigung sein oder über die ALTER ANY DATABASE EVENT NOTIFICATION-Berechtigung verfügen.  
  
 **So rufen Sie Informationen zu Ereignisbenachrichtigungen auf der Serverebene ab**  
  
-   [sys.server_event_notifications &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-server-event-notifications-transact-sql.md)  
  
> [!NOTE]  
>  Zum Anzeigen von Metadaten über Ereignisbenachrichtigungen in **sys.server_event_notifications** müssen mindestens die folgenden Voraussetzungen erfüllt sein: Sie müssen über die CONTROL- oder VIEW ANY DEFINITION-Berechtigung für den Server verfügen, Sie müssen der Anmeldename oder Besitzer der Ereignisbenachrichtigung sein, oder Sie müssen über die ALTER ANY EVENT NOTIFICATION-Berechtigung verfügen.  
  
 **So rufen Sie Informationen zu sämtlichen Ereignissen ab, die zur Auslösung von Ereignisbenachrichtigungen führen können**  
  
-   [sys.event_notification_event_types &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-event-notification-event-types-transact-sql.md)  
  
> [!NOTE]  
>  Diese Katalogsicht gibt keine Ereignisgruppen zurück.  
  
## Siehe auch  
 [Ereignisbenachrichtigungen](../../relational-databases/service-broker/event-notifications.md)  
  
  