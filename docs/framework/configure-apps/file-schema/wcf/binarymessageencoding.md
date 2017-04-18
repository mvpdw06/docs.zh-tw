---
title: "&lt;binaryMessageEncoding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;binaryMessageEncoding&gt;
定義二進位訊息編碼器，以二進位編碼網路上的 Windows Communication Foundation \(WCF\) 訊息。  
  
## 語法  
  
```  
  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10” />  
```  
  
## 屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### 屬性  
  
|屬性|描述|  
|--------|--------|  
|maxReadPoolSize|定義可同時讀取之訊息數目 \(在不配置新讀取器的情況下\) 的整數。  較大的集區大小可讓系統容許更多活動失效的情況，但是會產生較大的工作集。  預設值為 64。|  
|maxSessionSize|正整數，設定用於編碼的緩衝區大小 \(以位元組為單位\)。  較大的緩衝區會增加編碼速度，但是會犧牲工作集的大小。  預設值為 2048。|  
|maxWritePoolSize|定義可同時傳送之訊息數目 \(在不配置新寫入器的情況下\) 的整數。  較大的集區大小可讓系統容許更多活動失效的情況，但是會產生較大的工作集。  預設值為 16。|  
|messageVersion|指定已使用或必須使用的 SOAP 訊息和 WS\-Addressing 版本。|  
  
### 子項目  
  
|項目|描述|  
|--------|--------|  
|[\<readerQuotas\>](../Topic/%3CreaderQuotas%3E.md)|定義 SOAP 訊息複雜度的條件約束，而這些條件約束可由以此繫結所設定的端點處理。  此項目的型別為 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。|  
  
### 父項目  
  
|項目|描述|  
|--------|--------|  
|[\<繫結\>](../../../../../docs/framework/misc/binding.md)|定義自訂繫結的所有繫結功能。|  
  
## 備註  
 編碼是將訊息轉換成位元組序列的處理序，  解碼則是相反的處理序。  Windows Communication Foundation \(WCF\) 包含 SOAP 訊息的三種編碼類型：文字、二進位和訊息傳輸最佳化機制 \(MTOM\)。  
  
 `binaryMessageEncoding` 項目會指定 XML 的 .NET 二進位格式，並且提供指定字元編碼以及要使用之 SOAP 和 WS\-Addressing 版本的選項。  二進位訊息編碼器會以二進位編碼網路上的 Windows Communication Foundation \(WCF\) 訊息。  雖然這個編碼會讓訊息傳輸速度非常快，但是會失去以 WS\-\* 標準為基礎的互通性 \(Interoperability\)。  
  
## 範例  
  
```  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## 請參閱  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>   
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>   
 [訊息編碼](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)   
 [選擇訊息編碼器](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)   
 [繫結](../../../../../docs/framework/wcf/bindings.md)   
 [擴充繫結](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [自訂繫結](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)