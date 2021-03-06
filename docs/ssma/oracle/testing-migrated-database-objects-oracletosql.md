---
title: Testen von Datenbankobjekten (OracleToSQL) migriert | Microsoft Docs
ms.prod: sql
ms.prod_service: sql-tools
ms.component: ssma-oracle
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.suite: sql
ms.technology: ssma
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: f03ef5e1-66e6-4c84-ada2-252dd5ada82f
caps.latest.revision: 7
author: Shamikg
ms.author: Shamikg
manager: v-thobro
ms.openlocfilehash: da2327f94062d81a9b80e1884deb5150be494faa
ms.sourcegitcommit: 1740f3090b168c0e809611a7aa6fd514075616bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="testing-migrated-database-objects-oracletosql"></a>Testen von Datenbankobjekten (OracleToSQL) migriert
[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] Migration Assistant für Oracle-Tester (SSMA Tester) testet automatisch die Konvertierung der Datenbank-Objekt und die Datenmigration von SSMA vorgenommen werden. Nachdem Sie alle Schritte der SSMA-Migration abgeschlossen wurden, verwenden Sie SSMA Tester, stellen Sie sicher, dass die konvertierte Objekte die gleiche Weise funktioniert und alle Daten ordnungsgemäß übertragen wurde.  
  
Sie können die folgenden Objekttypen mit SSMA Tester testen:  
  
-   Tabellen  
  
-   Gespeicherte Prozeduren, einschließlich Pakete-Prozeduren.  
  
-   Benutzerdefinierte Funktionen, einschließlich Paketfunktionen.  
  
-   Ansichten.  
  
-   Eigenständige Anweisungen.  
  
SSMA-Tester führt zum Testen auf Oracle und ihren äquivalenten in ausgewählten Objekte [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)]. Anschließend vergleicht er die Ergebnisse entsprechend den folgenden Kriterien:  
  
-   Unterscheiden sich die Änderungen in Tabellendaten?  
  
-   Unterscheiden sich die Werte von Ausgabeparametern für Prozeduren und Funktionen?  
  
-   Führen Sie Funktionen, die die gleichen Ergebnisse zurück?  
  
-   Sind die Resultsets identisch?  
  
> [!NOTE]  
> Achtung! Verwenden Sie niemals SSMA Tester in Produktionssystemen. Während der Tester Ausführung werden dem Quellschema und Daten geändert. In der Zwischenzeit kann die vollständige Wiederherstellen des ursprünglichen Zustands für einige Typen von getesteten Code nicht möglich.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
Wenn Sie SSMA Tester verwenden möchten, installieren Sie SSMA-Oracle-Erweiterung-Paket mit der **installieren Tester Datenbank** aktiviert.  
  
Um den Vergleich der resultierenden Tabellendaten zu ermöglichen, legen die **generieren ROWID-Spalte** option **Ja** vor Beginn die schemakonvertierung. SSMA wird eine ROWID-Spalte für alle Tabellen hinzufügen, während der Ausführung der **Schema konvertieren** Befehl.  
  
Überprüfen Sie außerdem Folgendes:  
  
-   Oracle-Clienttools auf dem Computer installiert sind, in denen [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] ausgeführt wird.  
  
-   Common Language Runtime (CLR)-Integration aktiviert wurde, auf die [!INCLUDE[ssNoVersion](../../includes/ssnoversion_md.md)] -Datenbankmoduls.  
  
Beachten Sie, dass die aktuelle Version von SSMA Tester die parallele Ausführung von verschiedenen Benutzern auf demselben Server Quelle oder Ziel nicht unterstützt.  
  
## <a name="getting-started"></a>Erste Schritte  
[Erstellen von Testfällen &#40;OracleToSQL&#41;](../../ssma/oracle/creating-test-cases-oracletosql.md)  
  
## <a name="see-also"></a>Siehe auch  
[Installieren SSMA-Komponenten in SQLServer &#40;OracleToSQL&#41;](../../ssma/oracle/installing-ssma-components-on-sql-server-oracletosql.md)  
[Projekteinstellungen &#40;Konvertierung&#41; &#40;OracleToSQL&#41;](../../ssma/oracle/project-settings-conversion-oracletosql.md)  
  
