---
title: "Erstellen einer Wissensdatenbank | Microsoft Docs"
ms.custom: ""
ms.date: "06/04/2013"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "data-quality-services"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.dqs.kb.selectkb.f1"
  - "sql13.dqs.kb.newkb.f1"
ms.assetid: 2733a284-975f-4650-abcc-cc2aad074cab
caps.latest.revision: 20
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 20
---
# Erstellen einer Wissensdatenbank
  In diesem Thema wird beschrieben, wie eine Wissensdatenbank in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) erstellt und auf die Domänenverwaltung, die Wissensermittlung und das Hinzufügen einer Abgleichsrichtlinie vorbereitet wird.  
  
##  <a name="BeforeYouBegin"></a> Vorbereitungen  
  
###  <a name="Prerequisites"></a> Erforderliche Komponenten  
 Um eine Wissensdatenbank zu erstellen, müssen Sie [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] und [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)]installiert haben.  
  
###  <a name="Security"></a> Sicherheit  
  
####  <a name="Permissions"></a> Berechtigungen  
 Sie müssen über die dqs_kb_editor- oder dqs_administrator-Rolle in der DQS_MAIN-Datenbank verfügen, um eine Wissensdatenbank zu erstellen.  
  
##  <a name="Createaknowledgebase"></a> Erstellen einer Wissensdatenbank  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)] [Ausführen der Data Quality-Clientanwendung](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  Klicken Sie auf dem [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Neue Wissensdatenbank**.  
  
3.  Geben Sie einen Namen und eine Beschreibung für die neue Wissensdatenbank ein.  
  
4.  Wählen Sie unter **Wissensdatenbank erstellen aus**aus, worauf die neue Wissensdatenbank basieren soll:  
  
    -   Wählen Sie **Keine** aus, wenn die neue Wissensdatenbank nicht auf einer vorhandenen Wissensdatenbank oder Datendatei basieren soll.  
  
    -   Wählen Sie **Vorhandene Wissensdatenbank** aus, um eine Wissensdatenbank, die bereits auf [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]erstellt wurde, oder die Standardwissensdatenbank als Grundlage für die neue Wissensdatenbank zu verwenden. Wählen Sie die Wissensdatenbank aus der **Wissensdatenbank auswählen** Dropdown-Liste, oder klicken Sie **Durchsuchen** zum Anzeigen der **Wählen Sie eine Wissensdatenbank** Klicken Sie im Dialogfeld Wählen Sie einer vorhandenen Wissensdatenbank als Grundlage der neuen Knowledge Base auf, und klicken Sie dann auf **OK**. Wenn Sie eine Wissensdatenbank aus dem Tablett auswählen, werden die Domänen und Abgleichsregeln in der Wissensdatenbank im rechten Bereich des Dialogfelds angezeigt. Sie können auch auswählen, die **DQS-Daten** Wissensdatenbank, die die Standard-Wissensdatenbank verwendeten Out-of-the-Box-Domänen und Kenntnisse, die im Zusammenhang mit US-Unternehmen, die Adresse und die parteidaten enthält.  
  
    -   Wählen Sie **Aus DQS-Datei importieren** aus, um die neue Wissensdatenbank auf eine DQS-Datei auf dem [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)]zu basieren. Klicken Sie auf **Durchsuchen**, wählen Sie eine DQS-Datendatei mit der Erweiterung ".dqs" aus, und klicken Sie dann auf **OK**.  
  
5.  Wählen Sie unter **Aktivität auswählen**die Aktivität aus, die Sie für die neue Wissensdatenbank ausführen möchten:  
  
    -   Wählen Sie **Domänenverwaltung** aus, um die Wissensdatenbank zu erstellen, und öffnen Sie dann die Bildschirme, in denen Sie die Domänen in der Wissensdatenbank ändern.  
  
    -   Wählen Sie **Wissensermittlung** aus, um die Wissensdatenbank zu erstellen und um den Assistenten zum Analysieren eines Datenbeispiels zu öffnen, und füllen Sie die Domänen der Wissensdatenbank mit den Ergebnissen auf.  
  
    -   Wählen Sie **Abgleichsrichtlinie** aus, um eine Abgleichsrichtlinie zu erstellen und sie der Wissensdatenbank hinzuzufügen.  
  
6.  Klicken Sie auf **Erstellen**.  
  
##  <a name="FollowUp"></a> Nachverfolgung: Nach dem Erstellen einer Wissensdatenbank  
 Nachdem Sie eine Wissensdatenbank erstellt haben, werden ein Assistent für die Wissensermittlung, ein Assistent zum Erstellen einer Abgleichsrichtlinie oder Seiten für die Domänenverwaltung angezeigt. Weitere Informationen zu den Wissensermittlung, domänenverwaltung oder Abgleichsrichtlinie, finden Sie unter [Durchführen der Wissensermittlung](../data-quality-services/perform-knowledge-discovery.md), [Verwalten einer Domäne](../data-quality-services/managing-a-domain.md), oder [Erstellen einer Abgleichsrichtlinie](../data-quality-services/create-a-matching-policy.md).  
  
  