---
title: "外部活動驗證 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 外部活動驗證
這個範例示範如何將驗證邏輯加入至不是您撰寫的內建活動。驗證邏輯包含強制工作流程中的所有 <xref:System.Activities.Statements.If> 活動應設定 <xref:System.Activities.Statements.If.Then%2A> 屬性或 <xref:System.Activities.Statements.If.Else%2A> 屬性。此外，驗證邏輯也包含檢查工作流程中的所有 <xref:System.Activities.Statements.Pick> 活動都有一個以上的分支，否則會產生警告。  
  
## 範例詳細資料  
 這個範例會建立工作流程，其中每個活動執行個體都要驗證：<xref:System.Activities.Statements.If> 活動和 <xref:System.Activities.Statements.Pick> 活動。每個驗證行為都會建立 <xref:System.Activities.Validation.Constraint>。在這個範例中建立的條件約束是 `ConstraintError_IfShouldHaveThenOrElse` 和 `ConstraintWarning_PickHasOneBranch`。接著，將這些條件約束加入至 <xref:System.Activities.Validation.ValidationSettings> 執行個體的 `AdditionalConstraints` 集合。最後，呼叫 <xref:System.Activities.Validation.ActivityValidationServices> 的 `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 方法，以驗證工作流程中的活動，並將驗證結果印出至主控台。  
  
> [!NOTE]
>  您可以將原則條件約束加入至任何活動。例如，您可以將原則條件約束加入至 <xref:System.Activities.Statements.Sequence> 或 <xref:System.Activities.Statements.Parallel> 活動。  
  
#### 若要使用這個範例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 開啟 ExternalActivityValidation.sln 檔案。  
  
2.  若要建置此方案，請按下 CTRL\+SHIFT\+B。  
  
3.  若要執行方案，請按下 Ctrl \+ F5。  
  
> [!IMPORTANT]
>  這些範例可能已安裝在您的電腦上。請先檢查下列 \(預設\) 目錄，然後再繼續。  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目錄不存在，請移至[用於 .NET Framework 4 的 Windows Communication Foundation \(WCF\) 與 Windows Workflow Foundation \(WF\) 範例](http://go.microsoft.com/fwlink/?LinkId=150780)，以下載所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 範例。此範例位於下列目錄。  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`  
  
## 請參閱