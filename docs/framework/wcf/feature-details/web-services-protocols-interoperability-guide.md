---
title: "Web 服務通訊協定互通性手冊 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Web 服務通訊協定互通性手冊
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 會實作一些 Web 服務通訊協定。  許多這些通訊協定包含實作者應自行決定的一些選項和擴充點。  本主題提供 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 所實作的 Web 服務通訊協定清單。  本節中的其他主題則會提供每個受支援通訊協定的實作詳細資訊。  
  
## WCF 實作的 Web 服務通訊協定  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 透過通道支援 Web 服務 \(WS\) 基礎結構通訊協定，並透過合約功能支援 Web 服務應用程式通訊協定。  應用程式通訊協定的互通性是透過 XML 結構描述語言 1.0 \(XSD\) 和 Web 服務描述語言 \(WSDL\) 1.1 來達成。  
  
 基礎結構通訊協定互通性是由 WS\-\* 規格所提供。  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通道會支援一些 WS\-\* 基礎結構通訊協定。  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 通道是使用繫結元素來設定。  下表包含各種 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 繫結項目所實作的完整 WS\-\* 基礎結構通訊協定清單。  
  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 支援下表中的規格。  
  
|規格\/文件|連結|  
|------------|--------|  
|HTTP 1.1|[RFC 2616](http://go.microsoft.com/fwlink/?LinkId=90372)|  
|SOAP 1.1 HTTP 繫結|[簡易物件存取通訊協定 \(SOAP\) 1.1](http://go.microsoft.com/fwlink/?LinkId=90520)，第 7 節|  
|SOAP 1.2 HTTP 繫結|[SOAP 1.2 版第 2 部分：附加 \(第二版\)](http://go.microsoft.com/fwlink/?LinkId=95329)，第 7 節|  
  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 和 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 支援下表中的規格。  
  
|規格\/文件|連結|  
|------------|--------|  
|XML|[可延伸標記語言 \(XML\) 1.0 \(第四版\)](http://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1.1|[簡易物件存取通訊協定 \(SOAP\) 1.1](http://go.microsoft.com/fwlink/?LinkId=96687)|  
|SOAP 1.2 核心|[SOAP 1.2 版第 1 部分：訊息架構 \(第二版\)](http://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS\-Addressing 2004\/08|[Web 服務定址 \(WS\-Addressing\)](http://go.microsoft.com/fwlink/?LinkId=81239)|  
|W3C Web 服務定址 1.0 \- 核心|[Web 服務定址 1.0 \- 核心](http://go.microsoft.com/fwlink/?LinkId=96688)|  
|W3C Web 服務定址 1.0 \- SOAP 繫結|[Web 服務定址 1.0 \- SOAP 繫結](http://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web 服務定址 1.0 \- WSDL 繫結\*|[Web 服務定址 1.0 \- WSDL 繫結](http://go.microsoft.com/fwlink/?LinkId=96690)|  
|W3C Web 服務定址 1.0 中繼資料|[Web 服務定址 1.0 \- 中繼資料](http://www.w3.org/TR/ws-addr-metadata/)|  
|WSDL SOAP1.1 繫結|[Web 服務描述語言 \(WSDL\) 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)|  
|WSDL SOAP1.2 繫結|[SOAP 1.2 的 WSDL 1.1 繫結延伸](http://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 支援下表中的規格。  
  
|規格\/文件|連結|  
|------------|--------|  
|XOP|[XML 二進位最佳化套件](http://go.microsoft.com/fwlink/?LinkId=96714)|  
|MTOM \+ SOAP1.2 繫結|[SOAP 訊息傳輸最佳化機制](http://go.microsoft.com/fwlink/?LinkId=96713)|  
|MTOM SOAP 1.1 繫結|[MTOM 1.0 的 SOAP 1.1 繫結](http://go.microsoft.com/fwlink/?LinkId=96712)|  
|MTOM WS\-PolicyAssertions|即將發行。|  
  
 <xref:System.ServiceModel.Channels.SecurityBindingElement> 支援下表中的規格。  
  
|規格\/文件|連結|  
|------------|--------|  
|WSS：SOAP 訊息安全性 1.0|[Web 服務安全性：SOAP 訊息安全性 1.1](http://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS：使用者名稱權杖設定檔 1.0|[Web 服務安全性使用者名稱權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> 需要 Password\/@Type\=PasswordText \(預設\)|  
|WSS：X.509 權杖設定檔 1.0|[Web 服務安全性 X.509 憑證權杖設定檔](http://go.microsoft.com/fwlink/?LinkId=95335)|  
|WSS：SAML 1.1 權杖設定檔 1.0|[Web 服務安全性：SAML 權杖設定檔](http://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS：SOAP 訊息安全性 1.1|[Web 服務安全性：SOAP 訊息安全性 1.1](http://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS：使用者名稱權杖設定檔 1.1|[Web 服務安全性使用者名稱權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> 不會實作密碼架構金鑰衍生；<br /><br /> 需要 Password\/@Type\=PasswordText \(預設\)|  
|WSS：X509 權杖設定檔 1.1|[Web 服務安全性 X.509 憑證權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)|  
|WSS：Kerberos 權杖設定檔 1.1|[Web 服務安全性 Kerberos 權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)|  
|WSS：SAML 1.1 權杖設定檔 1.1|[Web 服務安全性 SAML 權杖設定檔 1.1](http://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS\-SecureConversation|[Web 服務安全轉換語言](http://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS\-Trust 1.4|[Web 服務信任語言](http://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS\-SecurityPolicy 2005\/07|[Web 服務安全轉換語言](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> 已由提交至 OASIS WS\-SX 技術委員會的勘誤表修訂。<br /><br /> [ws\-sx 訊息](http://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS\-ReliableMessaging 1.1|[Reliable Messaging Protocol 1.1 版](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 支援下表中的規格。  
  
|規格\/文件|連結|  
|------------|--------|  
|WS\-Coordination|[Web 服務協調](http://go.microsoft.com/fwlink/?LinkId=95324)|  
|WS\-AtomicTransaction|[Web 服務原子交易](http://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 <xref:System.ServiceModel.Description.MetadataExporter>、<xref:System.ServiceModel.Description.MetadataImporter>、<xref:System.ServiceModel.Description.WSDLExporter>、<xref:System.ServiceModel.Description.WSDLImporter> 和 <xref:System.ServiceModel.Description.MetadataResolver> 類別支援下列中繼資料規格：  
  
-   [XML 結構描述第一部分：結構第二版](http://go.microsoft.com/fwlink/?LinkId=3536)  
  
-   [XML 結構描述第二部分：資料型別第二版](http://go.microsoft.com/fwlink/?LinkId=40138)  
  
-   [WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=96160)  
  
-   [WS\-Policy 1.2](http://go.microsoft.com/fwlink/?LinkId=96705)  
  
-   [WS\-Policy 1.5](http://go.microsoft.com/fwlink/?LinkId=96706)  
  
-   [WS\-Policy 1.2 附件](http://go.microsoft.com/fwlink/?LinkId=96707)  
  
-   [WS\-MetadataExchange 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)  
  
-   [用於中繼資料擷取的 WS\-Transfer Get](http://go.microsoft.com/fwlink/?LinkId=96708)  
  
 此外，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 也會實作下列互通性設定檔：  
  
-   [Basic Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=69313)  
  
-   [簡單 SOAP 繫結 1.0](http://go.microsoft.com/fwlink/?LinkId=96710)  
  
-   [基本安全性設定檔 1.0 工作草稿](http://go.microsoft.com/fwlink/?LinkId=96711)  
  
## 請參閱  
 [系統提供的互通性繫結所支援的 Web 服務通訊協定](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)   
 [訊息通訊協定](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)   
 [資料合約結構描述參考](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)   
 [WSDL 與原則](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)   
 [安全性通訊協定](../../../../docs/framework/wcf/feature-details/security-protocols.md)   
 [Reliable Messaging Protocol 1.0 版](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)   
 [Reliable Messaging Protocol 1.1 版](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)   
 [交易通訊協定](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)   
 [內容交換通訊協定](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)