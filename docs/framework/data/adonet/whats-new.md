---
title: "ADO.NET 的新功能 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3bb65d38-cce2-46f5-b979-e5c505e95e10
caps.latest.revision: 25
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 25
---
# ADO.NET 的新功能
下列功能是 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 中 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 的新功能。  
  
## SqlClient Data Provider  
 下列功能在 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 中是 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 的新功能。  
  
-   ConnectRetryCount 和 ConnectRetryInterval 連接字串關鍵字 \(<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>\) 可讓您控制閒置連接恢復功能。  
  
-   [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 對應用程式的串流支援，當伺服器上的資料未結構化時才提供支援。  如需詳細資訊，請參閱 [SqlClient 資料流支援](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)。  
  
-   增加對非同步程式設計的支援。  如需詳細資訊，請參閱 [非同步程式設計](../../../../docs/framework/data/adonet/asynchronous-programming.md)。  
  
-   現在會將連接失敗記錄在擴充事件記錄中。  如需詳細資訊，請參閱[ADO.NET 中的資料追蹤](../../../../docs/framework/data/adonet/data-tracing.md)。  
  
-   SqlClient 現在支援 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 的高可用性、嚴重損壞修復功能、AlwaysOn。  如需詳細資訊，請參閱[高可用性、嚴重損壞修復的 SqlClient 支援](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-high-availability-disaster-recovery.md)。  
  
-   使用 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 驗證時，可將密碼當做 <xref:System.Security.SecureString> 來傳遞。  如需詳細資訊，請參閱 <xref:System.Data.SqlClient.SqlCredential>。  
  
-   當 `TrustServerCertificate` 為 False，且 `Encrypt` 為 True 時，[!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] SSL 憑證中的伺服器名稱 \(或 IP 位址\) 必須完全符合連接字串中所指定的伺服器名稱 \(或 IP 位址\)。  否則連接嘗試會失敗。  如需詳細資訊，請參閱 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 中有關 `Encrypt` 連線選項的說明。  
  
     如果此變更導致現有的應用程式不再連線，您可以使用下列其中一種方法修復應用程式：  
  
    -   簽發在 \[一般名稱\] \(CN\) 或 \[主體別名\] \(SAN\) 欄位中指定簡短名稱的憑證。  此解決方法適用於資料庫鏡像。  
  
    -   加入別名，將簡短名稱對應至完整網域名稱。  
  
    -   在連接字串中使用完整網域名稱。  
  
-   SqlClient 支援延伸的保護。  如需擴充保護的詳細資訊，請參閱[使用擴充保護連接至 Database Engine](http://go.microsoft.com/fwlink/?LinkId=219978)。  
  
-   SqlClient 支援連接至 LocalDB 資料庫。  如需詳細資訊，請參閱[LocalDB 的 SqlClient 支援](../../../../docs/framework/data/adonet/sql/sqlclient-support-for-localdb.md)。  
  
-   `Type System Version=SQL Server 2012;` 是傳遞至 `Type System Version` 連接屬性的新值。  `Type System Version=Latest;` 值現在已過時，並與 `Type System Version=SQL Server 2008;` 相等。  如需詳細資訊，請參閱<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>。  
  
-   SqlClient 提供額外的疏鬆資料行支援，這是在 SQL Server 2008 中新增的功能。  如果您的應用程式已存取使用疏鬆資料行之資料表中的資料，效能應該會有所提高。  <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> 的 IsColumnSet 資料行指出資料行是否為屬於資料行集的疏鬆資料行。  <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> 指出資料行是否為疏鬆資料行 \(如需詳細資訊，請參閱 [SQL Server 結構描述集合](../../../../docs/framework/data/adonet/sql-server-schema-collections.md)\)。  如需疏鬆資料行的詳細資訊，請參閱[使用疏鬆資料行](http://go.microsoft.com/fwlink/?LinkId=224244)。  
  
-   包含空間資料類型的 Microsoft.SqlServer.Types.dll 組件已從 10.0 版升級至 11.0 版。  參考此組件的應用程式可能會失敗。  如需詳細資訊，請參閱 [Database Engine 功能的重大變更](http://go.microsoft.com/fwlink/?LinkId=224367)。  
  
## ADO.NET Entity Framework  
 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)] 新增應用程式開發介面，可在搭配使用 Entity Framework 5.0 時啟用新案例。  如需 Entity Framework 5.0 之增強功能和新增功能的詳細資訊，請參閱下列主題：[新功能](http://go.microsoft.com/fwlink/?LinkID=251106)及 [Entity Framework 版本與版本設定](http://go.microsoft.com/fwlink/?LinkId=234899)。  
  
## 請參閱  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)   
 [ADO.NET 概觀](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [SQL Server 和 ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)   
 [What's New in WCF Data Services](http://msdn.microsoft.com/zh-tw/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)   
 [ADO.NET Managed 提供者和資料集開發人員中心](http://go.microsoft.com/fwlink/?LinkId=217917)