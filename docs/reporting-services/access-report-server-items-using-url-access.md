---
title: "Zugreifen auf Berichtsserverelemente &#252;ber den URL-Zugriff | Microsoft Docs"
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
  - "Verweisen auf URL-Elemente für den Berichtsserverzugriff"
  - "URL-Zugriff [Reporting Services], Berichtsserver"
ms.assetid: a58b4ca6-129d-45e9-95c7-e9169fe5bba4
caps.latest.revision: 40
author: "guyinacube"
ms.author: "asaxton"
manager: "erikre"
caps.handback.revision: 40
---
# Zugreifen auf Berichtsserverelemente &#252;ber den URL-Zugriff
  In diesem Thema wird beschrieben, wie Sie in einer Berichtsserver-Datenbank oder auf einer SharePoint-Website unter Verwendung von *rs:Command*=*Value* auf Katalogelemente mit unterschiedlichen Typen zugreifen. Es ist nicht erforderlich, diese Parameterzeichenfolge tatsächlich hinzuzufügen. Wenn Sie sie weglassen, wertet der Berichtsserver den Elementtyp aus und wählt den entsprechenden Parameterwert automatisch aus. Durch die Verwendung der *rs:Command*=*Value*-Zeichenfolge in der URL verbessert sich jedoch die Leistung des Berichtsservers.  
  
 Beachten Sie in den Beispielen unten die `_vti_bin` -Proxysyntax. Weitere Informationen zum Verwenden der Proxysyntax finden Sie unter [URL Access Parameter Reference](../reporting-services/url-access-parameter-reference.md).  
  
## Zugreifen auf einen Bericht  
 Verwenden Sie den *rs:Command*=*Render*-Parameter, um einen Bericht im Browser anzuzeigen. Beispiel:  
  
 **Systemeigenes Format** `http://myrshost/reportserver?/Sales/YearlySalesByCategory&rs:Command=Render`  
  
 **SharePoint** `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/YearlySalesByCategory&rs:Command=Render`  
  
> [!TIP]  
>  Es ist wichtig, dass die URL die `_vti_bin` -Proxysyntax zur Weiterleitung der Anforderung über SharePoint sowie den [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] -HTTP-Proxy enthält. Durch den Proxy wird der HTTP-Anforderung Kontext hinzugefügt. Dieser ist erforderlich, damit der Bericht auf Berichtsservern im SharePoint-Modus ordnungsgemäß ausgeführt wird.  
  
## Zugreifen auf eine Ressource  
 Verwenden Sie den *rs:Command*=*GetResourceContents*-Parameter, um auf eine Ressource zuzugreifen. Wenn die Ressource, z.B. ein Bild, mit dem Browser kompatibel ist, wird sie im Browser geöffnet. Andernfalls werden Sie aufgefordert, die Datei oder Ressource zu öffnen oder auf dem Datenträger zu speichern.  
  
 **Systemeigenes Format** `http://myrshost/reportserver?/Sales/StorePicture&rs:Command=GetResourceContents`  
  
 **SharePoint** `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/StorePicture.jpg&rs:Command=GetResourceContents`  
  
## Zugreifen auf eine Datenquelle  
 Verwenden Sie den Parameter *rs:Command*=*GetDataSourceContents*, um auf eine Datenquelle zuzugreifen. Wenn Ihr Browser XML unterstützt, wird die Datenquellendefinition angezeigt, wenn Sie ein für die Datenquelle authentifizierter Benutzer mit der Berechtigung **Read Contents** sind. Beispiel:  
  
 **Systemeigenes Format** `http://myrshost/reportserver?/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`  
  
 **SharePoint** `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales/AdventureWorks2012&rs:Command=GetDataSourceContents`  
  
 Die XML-Struktur kann Ähnlichkeit mit folgendem Beispiel haben:  
  
```  
<DataSourceDefinition>  
   <Extension>SQL</Extension>  
   <ConnectString>Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security Info=False;Initial Catalog=AdventureWorks2012;Data Source=MYSERVER1;</ConnectString>  
   <CredentialRetrieval>Integrated</CredentialRetrieval>  
   <WindowsCredentials>False</WindowsCredentials>  
   <ImpersonateUser>False</ImpersonateUser>  
   <Prompt />  
   <Enabled>True</Enabled>  
</DataSourceDefinition>  
```  
  
 Die Verbindungszeichenfolge wird auf Grundlage der **SecureConnectionLevel** -Einstellung des Berichtsservers zurückgegeben. Weitere Informationen zur **SecureConnectionLevel** -Einstellung finden Sie unter [Using Secure Web Service Methods](../reporting-services/report-server-web-service/net-framework/using-secure-web-service-methods.md).  
  
## Zugreifen auf den Inhalt eines Ordners  
 Verwenden Sie den *rs:Command*=*GetChildren*-Parameter, um auf den Inhalt eines Ordners zuzugreifen. Es wird eine generische Seite zur Ordnernavigation zurückgegeben, die Links zu den Unterordnern, Berichten, Datenquellen und Ressourcen im angeforderten Ordner enthält. Beispiel:  
  
 **Systemeigenes Format** `http://myrshost/reportserver?/Sales&rs:Command=GetChildren`  
  
 **SharePoint** `http://myspsite/subsite/_vti_bin/reportserver?http://myspsite/subsite/Sales&rs:Command=GetChildren`  
  
 Die angezeigte Benutzeroberfläche hat Ähnlichkeit mit dem Verzeichnissuchmodus, der von [!INCLUDE[msCoName](../includes/msconame-md.md)] IIS (Internet Information Server) verwendet wird. Die Versionsnummer, einschließlich der Buildnummer des Berichtsservers, wird ebenfalls unter der Ordnerliste angezeigt.  
  
## Siehe auch  
 [URL-Zugriff &#40;SSRS&#41;](../reporting-services/url-access-ssrs.md)   
 [URL-Zugriffsparameterverweis](../reporting-services/url-access-parameter-reference.md)  
  
  