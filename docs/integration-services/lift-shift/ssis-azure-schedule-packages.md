---
title: Planen der SIS-Pakete in Azure | Microsoft-Dokumentation
ms.date: 05/09/2018
ms.topic: conceptual
ms.prod: sql
ms.prod_service: integration-services
ms.component: lift-shift
ms.suite: sql
ms.custom: ''
ms.technology:
- integration-services
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 4bfad00425848189d88bd780296db00ec810b37c
ms.sourcegitcommit: 0cc2cb281e467a13a76174e0d9afbdcf4ccddc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2018
---
# <a name="schedule-the-execution-of-an-ssis-package-in-azure"></a>Planen der Ausführung eines SSIS-Pakets in Azure
Sie können die Ausführung von Paketen, die in der SSIS-Katalogdatenbank auf einem Azure SQL-Datenbankserver gespeichert sind, mithilfe einer der folgenden Planungsoptionen planen:
-   [Die Option „Zeitplan“ in SQL Server Management Studio (SSMS)](#ssms)
-   [Die Aktivität „SSIS-Paket ausführen“ von Azure Data Factory](#execute)
-   [Die Azure Data Factory-Aktivität für gespeicherte SQL Server-Prozeduren](#storedproc)
-   [SQL-Datenbank für elastische Aufträge](#elastic)
-   [SQL Server-Agent](#agent)

## <a name="ssms"></a> Planen eines Pakets mit SSMS

In SQL Server Management Studio (SSMS) können Sie mit der rechten Maustaste auf ein Paket klicken, das in der SSIS-Katalogdatenbank SSISDB bereitgestellt wird, und **Zeitplan** auswählen, um das Dialogfeld **Neuer Zeitplan** zu öffnen. Weitere Informationen finden Sie unter [Planen der Ausführung eines SSIS-Pakets in Azure mit SSMS](ssis-azure-schedule-packages-ssms.md).

Dieses Feature erfordert SQL Server Management Studio, Version 17.7 oder höher. Die neueste Version von SSMS können Sie unter [Herunterladen von SQL Server Management Studio (SSMS)](../../ssms/download-sql-server-management-studio-ssms.md) abrufen.

## <a name="execute"></a> Planen eines Pakets mit der Aktivität „SSIS-Paket ausführen“

Weitere Informationen dazu, wie Sie ein SSIS-Paket mithilfe der Aktivität „SSIS-Paket ausführen“ in Azure Data Factory planen, finden Sie unter [Ausführen eines SSIS-Pakets mit der SSIS-Aktivität in Azure Data Factory](https://docs.microsoft.com/azure/data-factory/how-to-invoke-ssis-package-ssis-activity).

## <a name="storedproc"></a> Planen eines Pakets mit der Aktivität „Gespeicherte Prozedur“

Weitere Informationen dazu, wie Sie ein SSIS-Paket mithilfe der Aktivität „Gespeicherte Prozedur“ in Azure Data Factory planen, finden Sie unter [Ausführen eines SSIS-Pakets mithilfe der Aktivität einer gespeicherten Prozedur in Azure Data Factory](https://docs.microsoft.com/azure/data-factory/how-to-invoke-ssis-package-stored-procedure-activity).

Weitere Informationen zu Version 1 von Data Factory finden Sie unter [Aufrufen eines SSIS-Pakets mithilfe einer Aktivität einer gespeicherten Prozedur in Azure Data Factory](https://docs.microsoft.com/azure/data-factory/v1/how-to-invoke-ssis-package-stored-procedure-activity).

## <a name="elastic"></a> Planen eines Pakets mit SQL-Datenbank für elastische Aufträge

Weitere Informationen zu elastischen Aufträgen auf SQL-Datenbank finden Sie unter [Verwalten von Scale Out-Clouddatenbanken](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-jobs-overview).

### <a name="prerequisites"></a>Voraussetzungen

Sie müssen zunächst folgende Schritte ausführen, damit Sie elastische Aufträge verwenden können, um SSIS-Pakete zu planen, die in der SSIS-Katalogdatenbank auf einem Azure SQL-Datenbankserver gespeichert sind:

1.  Installieren und Konfigurieren Sie die Komponenten für Aufträge für die elastische Datenbank. Informationen dazu finden Sie unter [Installieren von Aufträgen für die elastische Datenbank – Übersicht](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-jobs-service-installation).

2. Erstellen Sie datenbankbezogene Anmeldeinformationen, die Aufträge nutzen können, um Befehle an die SSIS-Katalogdatenbank zu senden. Informationen dazu finden Sie unter [CREATE DATABASE SCOPED CREDENTIAL (Transact-SQL) (Erstellen von datenbankbezogenen Anmeldeinformationen (Transact-SQL))](../../t-sql/statements/create-database-scoped-credential-transact-sql.md).

### <a name="create-an-elastic-job"></a>Erstellen eines elastischen Auftrags

Sie können den Auftrag erstellen, indem Sie ein Transact-SQL-Skript verwenden, das dem im folgenden Beispiel dargestellten Skript gleicht:

```sql
-- Create Elastic Jobs target group 
EXEC jobs.sp_add_target_group 'TargetGroup' 

-- Add Elastic Jobs target group member 
EXEC jobs.sp_add_target_group_member @target_group_name='TargetGroup', 
    @target_type='SqlDatabase', @server_name='YourSQLDBServer.database.windows.net',
    @database_name='SSISDB' 

-- Add a job to schedule SSIS package execution
EXEC jobs.sp_add_job @job_name='ExecutePackageJob', @description='Description', 
    @schedule_interval_type='Minutes', @schedule_interval_count=60

-- Add a job step to create/start SSIS package execution using SSISDB catalog stored procedures
EXEC jobs.sp_add_jobstep @job_name='ExecutePackageJob', 
    @command=N'DECLARE @exe_id bigint 
        EXEC [SSISDB].[catalog].[create_execution]
            @folder_name=N''folderName'', @project_name=N''projectName'',
            @package_name=N''packageName'', @use32bitruntime=0,
            @runinscaleout=1, @useanyworker=1, 
            @execution_id=@exe_id OUTPUT         
        EXEC [SSISDB].[catalog].[start_execution] @exe_id, @retry_count=0', 
    @credential_name='YourDBScopedCredentials', 
    @target_group_name='TargetGroup' 

-- Enable the job schedule 
EXEC jobs.sp_update_job @job_name='ExecutePackageJob', @enabled=1, 
    @schedule_interval_type='Minutes', @schedule_interval_count=60 
```

## <a name="agent"></a> Planen eines Pakets mit SQL Server-Agent

### <a name="prerequisite---create-a-linked-server"></a>Voraussetzung: Erstellen Sie einen Verbindungsserver

Bevor Sie SQL Server-Agent lokal zum Planen der Ausführung von auf einem Azure SQL-Datenbankserver gespeicherten Paket verwenden können, müssen Sie SQL-Datenbankserver als Verbindungsserver zu Ihrem lokalen SQL Server hinzufügen.

1.  **Einrichten des Verbindungsservers**

    ```sql
    -- Add the SSISDB database on your Azure SQL Database as a linked server to your SQL Server on premises
    EXEC sp_addlinkedserver
        @server='myLinkedServer', -- Name your linked server
        @srvproduct='',     
        @provider='sqlncli', -- Use SQL Server native client
        @datasrc='<server_name>.database.windows.net', -- Add your Azure SQL Database server endpoint
        @location=‘’,
        @provstr=‘’,
        @catalog='SSISDB'  -- Add SSISDB as the initial catalog
    ```

2.  **Einrichten der Anmeldeinformationen für den Verbindungsserver**

    ```sql
    -- Add your Azure SQL DB server admin credentials
    EXEC sp_addlinkedsrvlogin
        @rmtsrvname = 'myLinkedServer’,
        @useself = 'false’,
        @rmtuser = 'myUsername', -- Add your server admin username
        @rmtpassword = 'myPassword' -- Add your server admin password
    ```

3.  **Einrichten der Verbindungsserveroptionen**

    ```sql
    EXEC sp_serveroption 'myLinkedServer', 'rpc out', true;
    ```

Weitere Informationen finden Sie unter [Erstellen von Verbindungsservern](../../relational-databases/linked-servers/create-linked-servers-sql-server-database-engine.md) und [Linked Servers (Verbindungsserver)](../../relational-databases/linked-servers/linked-servers-database-engine.md).

### <a name="create-a-sql-server-agent-job"></a>Erstellen eines Auftrags für SQL Server-Agent

Erstellen Sie mithilfe eines Auftragsschritts einen Auftrag, der die gespeicherten SSIS-Katalog-Prozeduren `[catalog].[create_execution]` und `[catalog].[start_execution]` aufruft, um ein Paket lokal mit SQL Server-Agent zu planen. Weitere Informationen finden Sie unter [SQL Server Agent Jobs for Packages (Aufträge für SQL Server-Agent für Pakete)](../packages/sql-server-agent-jobs-for-packages.md).

1.  Stellen Sie in SQL Server Management Studio eine Verbindung mit der lokalen SQL Server-Datenbank her, auf der Sie den Auftrag erstellen möchten.

2.  Klicken Sie mit der rechten Maustaste auf den Knoten **SQL Server-Agent**, wählen Sie **Neu** aus, und klicken Sie anschließend auf **Auftrag**, damit das Dialogfeld **Neuer Auftrag** geöffnet wird.

3.  Wählen Sie im Dialogfeld **Neuer Auftrag** die Seite **Schritte** aus, und klicken Sie dann auf **Neu**, um das Dialogfeld **Neuer Auftragsschritt** zu öffnen.

4.  Wählen Sie im Dialogfeld **Neuer Auftragsschritt** `SSISDB` als **Datenbank** aus.

5.  Geben Sie im Feld **Befehl** ein Transact-SQL-Skript ein, das dem im folgenden Beispiel dargestellten Skript gleicht:

    ```sql
    -- T-SQL script to create and start SSIS package execution using SSISDB stored procedures
    DECLARE @return_value int, @exe_id bigint 

    EXEC @return_value = [YourLinkedServer].[SSISDB].[catalog].[create_execution] 
        @folder_name=N'folderName', @project_name=N'projectName', 
        @package_name=N'packageName', @use32bitruntime=0, @runincluster=1, @useanyworker=1,
        @execution_id=@exe_id OUTPUT 

    EXEC [YourLinkedServer].[SSISDB].[catalog].[set_execution_parameter_value] @exe_id,
        @object_type=50, @parameter_name=N'SYNCHRONIZED', @parameter_value=1

    EXEC [YourLinkedServer].[SSISDB].[catalog].[start_execution] @execution_id=@exe_id
    ```

6.  Stellen Sie die Konfiguration und die Planung des Auftrags fertig.

## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zu SQL Server-Agent finden Sie unter [SQL Server Agent Jobs for Packages (Aufträge für SQL Server-Agent für Pakete)](../packages/sql-server-agent-jobs-for-packages.md).

Weitere Informationen zu elastischen Aufträgen auf SQL-Datenbank finden Sie unter [Verwalten von Scale Out-Clouddatenbanken](https://docs.microsoft.com/azure/sql-database/sql-database-elastic-jobs-overview).
