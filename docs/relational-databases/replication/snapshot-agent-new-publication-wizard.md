---
title: "Momentaufnahme-Agent (Assistent f&#252;r neue Ver&#246;ffentlichung) | Microsoft Docs"
ms.custom: ""
ms.date: "03/01/2017"
ms.prod: "sql-server-2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "replication"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "sql13.rep.newpubwizard.configuresnapshotagent.f1"
ms.assetid: 0257d4ee-1f7b-49fd-b4ef-65bfc1ef6951
caps.latest.revision: 29
author: "BYHAM"
ms.author: "rickbyh"
manager: "jhubbard"
caps.handback.revision: 29
---
# Momentaufnahme-Agent (Assistent f&#252;r neue Ver&#246;ffentlichung)
  Der Momentaufnahme-Agent erstellt Dateien, die das Veröffentlichungsschema und die Daten enthalten, die zum Initialisieren neuer Abonnements verwendet werden. Standardmäßig wird der Momentaufnahme-Agent sofort nach dem Erstellen der Veröffentlichung im Assistenten für neue Veröffentlichung ausgeführt. Danach wird der Agent nach einem angegebenen Zeitplan ausgeführt. Ob der Agent bei jeder Ausführung neue Momentaufnahmedateien erstellt, hängt vom Typ der Replikation und den ausgewählten Optionen ab. Weitere Informationen finden Sie unter [Erstellen und Anwenden der Momentaufnahme](../../relational-databases/replication/create-and-apply-the-snapshot.md).  
  
 Bei Mergeveröffentlichungen, die parametrisierte Filter verwenden, müssen Sie für jede Datenpartition eine Momentaufnahme erstellen, nachdem die Veröffentlichungsmomentaufnahme abgeschlossen ist. Weitere Informationen finden Sie unter [Snapshots for Merge Publications with Parameterized Filters](../../relational-databases/replication/snapshots-for-merge-publications-with-parameterized-filters.md).  
  
## Optionen  
 **Snapshot sofort erstellen** (Mergereplikation) oder **Snapshot sofort erstellen und zum Initialisieren von Abonnements verfügbar halten** (Transaktionsreplikation)  
 Aktivieren Sie dieses Kontrollkästchen, um sofort nach dem Abschließen des Assistenten für neue Veröffentlichung eine Momentaufnahme zu erstellen. Deaktivieren Sie dieses Kontrollkästchen, wenn Sie planen, die Momentaufnahmeeigenschaften im Dialogfeld **Veröffentlichungseigenschaften** vor dem Erstellen einer Momentaufnahme zu ändern, oder wenn Sie den Abonnenten ohne Momentaufnahme initialisieren werden. Weitere Informationen finden Sie unter [eine Transaktionsabonnements ohne Momentaufnahme initialisieren](../../relational-databases/replication/initialize-a-transactional-subscription-without-a-snapshot.md).  
  
> [!NOTE]  
>  Der Assistent fordert möglicherweise zur Eingabe einer Verbindung mit dem Verteiler auf, um den entsprechenden Auftrag für den Verteilungs- oder Merge-Agent zu starten.  
  
 **Ausführung des Momentaufnahme-Agents zu folgenden Zeitpunkten planen**  
 Akzeptieren Sie den Standardzeitplan für die Ausführung des Snapshot-Agents, oder klicken Sie auf **Ändern** um einen Zeitplan anzugeben.  
  
## Siehe auch  
 [Erstellen einer Veröffentlichung](../../relational-databases/replication/publish/create-a-publication.md)   
 [Erstellen und Anwenden der Anfangsmomentaufnahme](../../relational-databases/replication/create-and-apply-the-initial-snapshot.md)   
 [Anzeigen und Ändern von Veröffentlichungseigenschaften](../../relational-databases/replication/publish/view-and-modify-publication-properties.md)   
 [Initialisieren eines Abonnements mit einer Momentaufnahme](../../relational-databases/replication/initialize-a-subscription-with-a-snapshot.md)   
 [Veröffentlichen von Daten und Datenbankobjekten](../../relational-databases/replication/publish/publish-data-and-database-objects.md)   
 [Replikations-Agents (Übersicht)](../../relational-databases/replication/agents/replication-agents-overview.md)  
  
  