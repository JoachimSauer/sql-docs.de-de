---
title: "Report Server-Windows-Dienst (MSSQLServer) 107 | Microsoft Docs"
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
  - "MSSQLServer 107 (Fehler)"
ms.assetid: 52b5704b-27f9-400a-a821-d8fa0786afe4
caps.latest.revision: 20
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 20
---
# Report Server-Windows-Dienst (MSSQLServer) 107
    
## Details  
  
|||  
|-|-|  
|Produktname|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Ereignis-ID|107|  
|Ereignisquelle|Report Server-Windows-Dienst|  
|Komponente|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|Meldungstext|Es kann keine Verbindung zwischen dem Report Server-Windows-Dienst (MSSQLSERVER) und der Berichtsserver-Datenbank hergestellt werden.|  
  
## Erklärung  
 Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Report Server-Dienst kann keine Verbindung zur Berichtsserver-Datenbank herstellen. Dieser Fehler tritt während des Neustarts eines Diensts auf, wenn keine Verbindung zur Berichtsserver-Datenbank hergestellt werden kann. Der Fehler tritt unter den folgenden Bedingungen auf:  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Dienst wird beim Start des Report Server-Diensts nicht ausgeführt.  
  
-   Die Verbindung zum [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Dienst schlägt fehl, da Remoteverbindungen oder das TCP/IP-Protokoll nicht aktiviert sind.  
  
-   Die Berichtsserver-Datenbank wurde nicht ordnungsgemäß konfiguriert.  
  
-   Das Dienstkonto wurde nicht ordnungsgemäß konfiguriert, oder das Konto verfügt nicht mehr über die Berechtigung für die Berichtsserver-Datenbank. Dies tritt auf, wenn Sie beim Einrichten des Kontos oder der Berichtsserver-Datenbank nicht das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool verwenden.  
  
## Benutzeraktion  
 Starten Sie den [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Dienst, wenn er nicht bereits ausgeführt wird, und stellen Sie sicher, dass für das TCP/IP-Protokoll Remoteverbindungen zulässig sind.  
  
 Verwenden Sie zum Konfigurieren der Berichtsserver-Datenbank und des Dienstkontos das [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Konfigurationstool.  
  
## Nur intern  
  
## Siehe auch  
 [Konfigurieren des Berichtsserver-Dienstkontos &#40;SSRS-Konfigurations-Manager&#41;](../../reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager.md)   
 [Reporting Services-Konfigurations-Manager &#40;einheitlicher Modus&#41;](../../reporting-services/install-windows/reporting-services-configuration-manager-native-mode.md)   
 [Starten und Beenden des Berichtsserverdiensts](../../reporting-services/report-server/start-and-stop-the-report-server-service.md)  
  
  