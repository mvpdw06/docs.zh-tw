---
title: "Windows Communication Foundation 4.5 的新功能 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF [WCF], 新功能"
  - "Windows Communication Foundation [WCF], 新功能"
ms.assetid: 7e93fe73-af93-46b5-9f63-32f761ee40cf
caps.latest.revision: 35
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 35
---
# Windows Communication Foundation 4.5 的新功能
本主題討論 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 中的新功能。  
  
## WCF 簡化功能  
 為了使 WCF 4.5 應用程式更容易開發和維護，我們已投入了大量的努力。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF 簡化功能](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### 以工作為基礎的非同步支援  
 根據預設，\[加入服務參考\] 可產生傳回工作的非同步服務作業方法。也可使用同步和非同步方法。使用這種全新且以工作為基礎的非同步程式設計模型，可讓您以非同步方式呼叫服務作業。當您呼叫所產生的 Proxy 方法時，WCF 會建構 Task 物件以代表非同步作業，並將該 Task 傳回給您。作業與 Task 會同時完成。在實作非同步作業時，您可將此實作為以工作為基礎的非同步作業。如需詳細資訊，請參閱 [同步和非同步作業](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)。  
  
### 簡化產生的組態檔  
 當您在 Visual Studio 中加入服務參考，或使用 SvcUtil.exe 工具時，用戶端組態檔就會產生。在舊版 WCF 中，這些組態檔會包含所有繫結屬性的值，即使值為預設值，也是如此。在 WCF 4.5 中產生的組態檔只會包含那些設定成非預設值的繫結屬性。  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [WCF 簡化功能](../../../docs/framework/wcf/wcf-simplification-features.md)  
  
### 合約優先開發  
 WCF 現可支援合約優先開發。svcutl.exe 有 \/serviceContract 參數可讓您從 WSDL 文件產生服務與資料合約。  
  
### 從可攜式子集專案加入服務參考  
 可攜式子集專案可讓 .NET 組件程式設計人員維護單一來源的樹狀目錄和建置系統，同時還支援多個 .NET 平台 \(桌上型電腦、Silverlight、Windows Phone 和 XBOX\)。可攜式子集專案僅參考 .NET 可攜式程式庫，這些程式庫是可用於任何核心 .NET 平台的 .NET Framework 組件。開發人員的體驗與在任何其他 WCF 用戶端應用程式內加入服務參考相同。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][將服務參考加入至可攜式子集專案](../../../docs/framework/wcf/add-service-reference-in-a-portable-subset-project.md).  
  
### ASP.NET 相容模式預設值已變更  
 WCF 會在寫入 WCF 服務時提供 ASP.NET 相容模式，將 ASP.NET HTTP 管線功能的完整存取權限授與開發人員。若要使用這個模式，您必須在 web.config 的 [\<serviceHostingEnvironment\>](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) 區段中將 `aspNetCompatibilityEnabled` 屬性設定為 true。此外，這個 appDomain 中的任何服務還必須將其 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> 上的 `RequirementsMode` 屬性設定為 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode> 或 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>。預設值為 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> 現在會設定為 <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode>。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][What's New in Windows Communication Foundation](../../../docs/framework/wcf/whats-new.md)和[WCF 服務與 ASP.NET](../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)。  
  
### 新的傳輸預設值  
 為了簡化組態，我們已變更一些傳輸屬性的預設值。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF 簡化功能](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### XmlDictionaryReaderQuotas  
 <xref:System.Xml.XmlDictionaryReaderQuotas> 包含 XML 字典讀取器的可設定配額值，這些值會限制編碼器在建立訊息時使用的記憶體量。雖然這些配額是可設定的，但變更為預設值可降低開發人員必須明確設定這些值的機率。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF 簡化功能](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
### WCF 組態驗證  
 Visual Studio 現在有一部分建置流程會針對專案中定義的屬性來驗證 WCF 組態檔。如果驗證失敗，將會在 Visual Studio 中顯示驗證錯誤或警告的清單。  
  
### XML 編輯器工具提示  
 為了協助新的和現有的 WCF 服務開發人員設定其服務，現在每個屬於服務組態檔之一部分的組態項目及其屬性，Visual Studio XML 編輯器都有提供工具提示。  
  
## 資料流的改進  
 加入對真正非同步資料流處理的支援，如果接收端不是正在讀取或是讀取速度緩慢，傳送端現在不會封鎖執行緒，延展性因此提升。移除對用戶端發送資料流訊息至 IIS 裝載之 WCF 服務時的訊息緩衝限制。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][WCF 簡化功能](../../../docs/framework/wcf/wcf-simplification-features.md).  
  
## 簡化透過 HTTPS 向 IIS 公開端點  
 已加入 HTTPS 通訊協定對應以簡化透過 HTTPS 公開端點的程序。若要啟用 HTTPS 端點，請確定您的網站已設定 HTTPS 繫結和 SSL 憑證，然後只需為裝載服務的虛擬目錄啟用 HTTPS 即可。如果服務的中繼資料已啟用，也會透過 HTTPS 加以公開。  
  
## 產生單一 WSDL 文件  
 某些協力廠商 WSDL 處理堆疊無法處理透過 xsd:import 相依於其他文件的 WSDL 文件。WCF 現在允許您指定以單一文件來傳回所有 WSDL 資訊。如需要求單一 WSDL 文件，當您向服務要求中繼資料時，請將 "?singleWSDL" 附加至 URI。  
  
## WebSocket 支援  
 WebSockets 是透過連接埠 80 和 443 提供真正雙向通訊的技術，其效能特性與 TCP 類似。為了支援透過 WebSocket 傳輸進行通訊，我們已加入兩個新的繫結。<xref:System.ServiceModel.NetHttpBinding> 和 <xref:System.ServiceModel.NetHttpsBinding>。如需詳細資訊，請參閱 [系統提供的繫結](../../../docs/framework/wcf/system-provided-bindings.md)。  
  
## 新的傳輸預設值  
 下列資料表說明已變更的設定以及可找到其他資訊的位置。  
  
|屬性|開啟|新的預設值|如需詳細資訊，請參閱|  
|--------|--------|-----------|----------------|  
|channelInitializationTimeout|<xref:System.ServiceModel.NetTcpBinding>|30 秒|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.ChannelInitializationTimeout%2A>|  
|listenBacklog|<xref:System.ServiceModel.NetTcpBinding>|12 \* 處理器的數量|<xref:System.ServiceModel.NetTcpBinding.ListenBacklog%2A>|  
|maxPendingAccepts|ConnectionOrientedTransportBindingElement<br /><br /> SMSvcHost.exe|2 \* 用於傳輸的處理器數量<br /><br /> 4 \* 用於 SMSvcHost.exe 的處理器數量|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingAccepts%2A> [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/zh-tw/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
|maxPendingConnections|ConnectionOrientedTransportBindingElement|12 \* 處理器的數量|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement.MaxPendingConnections%2A>|  
|receiveTimeout|SMSvcHost.exe|30 秒|[Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/zh-tw/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)|  
  
## XML 編輯器工具提示  
 為了協助新的和現有的 WCF 服務開發人員設定其服務，現在每個屬於服務組態檔之一部分的組態項目及其屬性，Visual Studio XML 編輯器都有提供工具提示。  
  
## 在程式碼中設定 WCF 服務  
 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 可讓開發人員使用組態檔或程式碼來設定服務。當服務需要在部署後進行設定時，組態檔非常有用。使用組態檔時，IT 專業人員只需更新組態檔，不必重新編譯。但是組態檔可能會很複雜而難以維護。由於不支援組態檔偵錯，而且組態項目是以名稱來參考，這使得製作組態檔容易出錯且難度增加。[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 也允許您以程式碼來設定服務。在舊版 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] \(4.0 及更早版本\) 的在自我裝載案例中，您可以輕鬆使用程式碼來設定服務，因為 <xref:System.ServiceModel.ServiceHost> 類別可讓您在呼叫 ServiceHost.Open 之前設定端點和行為。但是在 Web 裝載案例中，您就無法存取 <xref:System.ServiceModel.ServiceHost> 類別。為了設定 Web 裝載服務，您需要建立會建立 <xref:System.ServiceModel.ServiceHost> 的 <xref:System.ServiceModel.ServiceHostFactory>，並執行任何所需的設定。從 .NET 4.5 開始，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 提供了更簡單的方法，以程式碼來設定自我裝載和 Web 裝載服務。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][在程式碼中設定 WCF 服務](../../../docs/framework/wcf/configuring-wcf-services-in-code.md).  
  
## ChannelFactory 快取  
 WCF 用戶端應用程式會使用 <xref:System.ServiceModel.ChannelFactory%601> 類別來建立與 WCF 服務的通訊通道。建立 <xref:System.ServiceModel.ChannelFactory%601> 執行個體會產生額外負荷，因為這涉及到下列作業：  
  
1.  建構 <xref:System.ServiceModel.Description.ContractDescription> 樹狀結構  
  
2.  反映所有必要的 CLR 型別  
  
3.  建構通道堆疊  
  
4.  處置資源  
  
 為了盡量減少這種負荷，WCF 可以在您使用 WCF 用戶端 Proxy 時快取通道處理站。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][通道處理站和快取](../../../docs/framework/wcf/feature-details/channel-factory-and-caching.md).  
  
## 壓縮和二進位編碼器  
 從 WCF 4.5 開始，WCF 二進位編碼器加入壓縮的支援。壓縮型別是透過 <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A> 屬性來設定。用戶端和服務都必須設定 <xref:System.ServiceModel.Channels.BinaryMessageEncodingElement.CompressionFormat%2A> 屬性。壓縮適用於 HTTP、HTTPS 和 TCP 通訊協定。如果用戶端指定要使用壓縮，但服務不支援這項功能，則會擲回通訊協定例外狀況以表示通訊協定不相符。[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][選擇訊息編碼器](../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
  
## UDP  
 已加入 UDP 傳輸的支援，這可讓開發人員撰寫使用「射後不理」\(Fire And Forget\) 傳訊的服務。用戶端傳送訊息給服務，而不期待服務發出任何回應。  
  
## 多重驗證支援  
 已加入支援，如同 IIS 的支援一樣，在使用 HTTP 傳輸與傳輸安全性時，於單一 WCF 端點上支援多個驗證模式。IIS 允許您在虛擬目錄上啟用多個驗證模式，這項功能可讓單一 WCF 端點支援裝載 WCF 服務之虛擬目錄所啟用的多個驗證模式。  
  
## IDN 支援  
 已加入支援，並允許具有國際化網域名稱的 WCF 服務。如需詳細資訊，請參閱[WCF 及國際化網域名稱](../../../docs/framework/wcf/feature-details/wcf-and-internationalized-domain-names.md)。  
  
## HttpClient  
 已加入名稱為 <xref:System.Net.Http.HttpClient> 的新類別，使得處理 HTTP 要求大為方便。如需詳細資訊，請參閱[使應用程式具備社交功能並與 HTTP 服務連接](http://go.microsoft.com/fwlink/?LinkId=231886)和 [HTTP 用戶端範例](http://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)。  
  
## 組態 Intellisense  
 在組態檔中，對於專案內定義之自訂屬性的屬性值現可支援 Intellisense 功能，以協助您快速準確地處理組態檔。  
  
## 組態工具提示  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 項目和屬性目前在 XML 編輯器中會有工具提示，以協助您輕鬆並準確地識別項目或屬性的用途。  
  
## 貼上資料做為類別  
 在 WCF 專案中，定義於 XML 的資料型別 \(例如服務中所公開的項目\) 可以直接貼到程式碼頁面上。XML 型別會以 CLR 型別貼上。如需詳細資訊，請參閱 [從 XML 產生資料型別類型](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)。  
  
## WebServiceHost 和預設端點  
 在 Visual Studio 2010 中，不論您是否明確指定端點，WebServiceHost 都會自動建立預設端點。在 Visual Studio 2012 中，WebServiceHost 只有在沒有明確加入的端點時才會建立預設端點。如果您的用戶端想要預設端點，您可以明確加入端點並將用戶端指向該端點。或者，您可以將下列設定加入您應用程式的組態檔，告知 WCF 還原成之前的行為  
  
```xml  
<appSettings>  
    <add key="wcf:webservicehost:enableautomaticendpointscompatability" value="true"/>  
  </appSettings>  
  
```  
  
## IHttpCookieContainerManager  
 這個由 <xref:System.ServiceModel.Channels.HttpChannelFactory> 公開的介面，可讓您在用戶端上更輕鬆地使用 Cookie。當繫結上的 AllowCookies 設定為 true 時，您可使用下列程式碼存取 Cookie：  
  
```csharp  
IHttpCookieContainerManager cookieManager = factory.GetProperty<IHttpCookieContainerManager>();   
System.Net.CookieContainer container = cookieManager.CookieContainer;  
  
```  
  
 之後，您即可從 <xref:System.Net.CookieContainer> 擷取或設定 Cookie。當 AllowCookies 設為 false 時，您可使用 <xref:System.ServiceModel.OperationContext> 手動擷取 Cookie，並使用另一個 <xref:System.ServiceModel.OperationContext> 或訊息偵測器，在其他要求中傳送此 Cookie。IHttpCookieContainerManager 介面可讓您驗證使用者與服務，並使用該服務傳回的驗證 Cookie 來驗證其他服務。