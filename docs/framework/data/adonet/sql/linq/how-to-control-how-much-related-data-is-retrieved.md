---
title: "HOW TO：控制擷取的相關資料量 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# HOW TO：控制擷取的相關資料量
使用 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 方法可指定與您主要目標有關、應該同時擷取的資料。  例如，如果您預先得知需要客戶訂單的相關資訊，則可以使用 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>，以確保在擷取客戶資訊的同時也會擷取訂單資訊。  這種方法只要存取一次資料庫，就可以同時取得兩個資訊集。  
  
> [!NOTE]
>  您可以將叉積擷取為一個大型投影 \(如在找到客戶時擷取訂單\)，以擷取與查詢之主要目標相關的資料。  但是這種方法通常有其缺點。  例如，其結果只是投影，而不是 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 可以變更和持續的實體。而且您可能會擷取到很多不需要的資料。  
  
## 範例  
 在下列範例中，執行查詢時，會擷取位在倫敦 \(London\) 之所有 `Customers` 的所有 `Orders`。  如此一來，後續存取 `Customer` 物件上的 `Orders` 屬性時，便不會觸發新的資料庫查詢。  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## 請參閱  
 [查詢資料庫](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)