---
title: "Paket ausw&#228;hlen | Microsoft Docs"
ms.custom: ""
ms.date: "03/14/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "integration-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dts.designer.selectapackage.f1"
helpviewer_keywords: 
  - "Paket auswählen (Dialogfeld)"
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
caps.latest.revision: 16
author: "douglaslMS"
ms.author: "douglasl"
manager: "jhubbard"
caps.handback.revision: 16
---
# Paket ausw&#228;hlen
  Mithilfe des Dialogfelds **Paket auswählen** können Sie das Paket angeben, von dem der Task Nachrichtenwarteschlange Nachrichten empfangen kann.  
  
## Statische Optionen  
 **Speicherort**  
 Geben Sie den Speicherort des Pakets an. Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.  
  
|Wert|Description|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|Legt den Speicherort als Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]fest. Wenn Sie diesen Wert auswählen, werden die dynamischen Optionen **Server**, **Windows-Authentifizierung verwenden**, **SQL Server-Authentifizierung verwenden**, **Benutzername**und **Kennwort**angezeigt.|  
|DTSX-Datei|Legt als Speicherort eine DTSX-Datei fest. Wenn Sie diesen Wert auswählen, wird die dynamische Option **Dateiname**angezeigt.|  
  
## Dynamische Optionen für Location  
  
### Location = SQL Server  
 **Paketname**  
 Wählen Sie ein Paket aus, das auf dem angegebenen Server gespeichert ist.  
  
 **Server**  
 Geben Sie einen Servernamen an, oder wählen Sie einen Server aus der Liste aus.  
  
 **Windows-Authentifizierung verwenden**  
 Klicken Sie auf diese Option, wenn die Windows-Authentifizierung verwendet werden soll.  
  
 **SQL Server-Authentifizierung verwenden**  
 Klicken Sie auf diese Option, wenn die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwendet werden soll.  
  
 **Benutzername**  
 Wenn Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden, geben Sie einen Benutzernamen an, der zur Anmeldung beim Server verwendet wird.  
  
 **Kennwort**  
 Geben Sie ein Kennwort an, falls Sie die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Authentifizierung verwenden.  
  
### Speicherort = DTSX-Datei  
 **Dateiname**  
 Geben Sie den Pfad eines Pakets an, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(…)**, um das Paket zu suchen.  
  
## Siehe auch  
 [Nachrichtenwarteschlange (Task)](../../integration-services/control-flow/message-queue-task.md)  
  
  