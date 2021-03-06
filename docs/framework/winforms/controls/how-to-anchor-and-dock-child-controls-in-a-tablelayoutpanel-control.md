---
title: "如何：錨定和停駐 TableLayoutPanel 控制項中的子控制項 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "net.ComponentModel.StyleCollectionEditor.TLP.AnchorDock"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "子控制項, 錨定和停駐"
  - "控制項 [Windows Form], 子項"
  - "版面配置 [Windows Form], 子控制項"
  - "TableLayoutPanel 控制項 [Windows Form], 子控制項"
ms.assetid: 0d267c35-25f1-49b8-8976-c64e8f0ddc0b
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 如何：錨定和停駐 TableLayoutPanel 控制項中的子控制項
<xref:System.Windows.Forms.TableLayoutPanel> 控制項在其子控制項中支援 <xref:System.Windows.Forms.Control.Anchor%2A> 和 <xref:System.Windows.Forms.Control.Dock%2A> 屬性。  
  
### 若要對齊 TableLayoutPanel 儲存格中的子控制項  
  
1.  請在表單上建立 <xref:System.Windows.Forms.TableLayoutPanel> 控制項。  
  
2.  設定 <xref:System.Windows.Forms.TableLayoutPanel> 控制項的 <xref:System.Windows.Forms.TableLayoutPanel.ColumnCount%2A> 值和 <xref:System.Windows.Forms.TableLayoutPanel.RowCount%2A> 屬性設為 1。  
  
3.  在 <xref:System.Windows.Forms.TableLayoutPanel> 控制項中建立 <xref:System.Windows.Forms.Button> 控制項。  <xref:System.Windows.Forms.Button> 會佔用儲存格的左上角。  
  
4.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值為 `Left`。  <xref:System.Windows.Forms.Button> 控制項移到與儲存格左框線對齊。  
  
    > [!NOTE]
    >  此行為不同於其他容器控制項的行為。  在其他容器控制項中，當 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性被設定時，子控制項不會移動，而且當 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性被設定時，錨定的控制項與父容器界限之間的距離固定。  
  
5.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值為 `Top, Left`。  <xref:System.Windows.Forms.Button> 控制項移到佔用儲存格左上角。  
  
6.  以 `Top, Right` 的值重複步驟 5，以移動 <xref:System.Windows.Forms.Button> 控制項至儲存格右上角。  以 `Bottom, Left` 和 `Bottom, Right` 的值重複進行。  
  
### 若要自動縮放 TableLayoutPanel 儲存格中的子控制項  
  
1.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值為 `Left, Right`。  會調整 <xref:System.Windows.Forms.Button> 控制項的大小，自動縮放整個儲存格。  
  
    > [!NOTE]
    >  此行為不同於其他容器控制項的行為。  在其他容器控制項中，當 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性設定為 `Left, Right` 或 `Top, Bottom` 時，不會調整子控制項的大小。  
  
2.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值為 `Top, Bottom`。  會調整 <xref:System.Windows.Forms.Button> 控制項的大小，從頂端到底部自動縮放儲存格。  
  
3.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值為 `Top, Bottom, Left, Right`。  調整 <xref:System.Windows.Forms.Button> 控制項的大小以填滿儲存格。  
  
4.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值為 `None`。  調整 <xref:System.Windows.Forms.Button> 控制項的大小，並在儲存格中置中。  
  
5.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Dock%2A> 屬性值為 <xref:System.Windows.Forms.DockStyle>。  <xref:System.Windows.Forms.Button> 控制項移到與儲存格左框線對齊。  會保留 <xref:System.Windows.Forms.Button> 控制項寬度，但會調整它高度的大小，以垂直方式填滿儲存格。  
  
    > [!NOTE]
    >  這與在其他容器控制項中發生的行為相同。  
  
6.  變更 <xref:System.Windows.Forms.Button> 控制項的 <xref:System.Windows.Forms.Control.Dock%2A> 屬性值為 <xref:System.Windows.Forms.DockStyle>。  調整 <xref:System.Windows.Forms.Button> 控制項的大小以填滿儲存格。  
  
## 範例  
 下圖顯示錨定在 5 個不同 <xref:System.Windows.Forms.TableLayoutPanel> 資料格的 5 個按鈕。  
  
 ![TableLayoutPanel 錨定](../../../../docs/framework/winforms/controls/media/vs-tlpanchor.png "VS\_TLPanchor")  
  
 下圖顯示錨定在 4 個不同 <xref:System.Windows.Forms.TableLayoutPanel> 儲存格角落的 4 個按鈕。  
  
 ![TableLayoutPanel 錨定](../../../../docs/framework/winforms/controls/media/vs-tlpanchor2.png "VS\_TLPanchor2")  
  
 下圖顯示藉由錨定在 3 個不同 <xref:System.Windows.Forms.TableLayoutPanel> 儲存格來自動縮放 3 個按鈕。  
  
 ![TableLayoutPanel 錨定](../../../../docs/framework/winforms/controls/media/vs-tlpanchor3.gif "VS\_TLPAnchor3")  
  
 下列程式碼範例示範所有 <xref:System.Windows.Forms.TableLayoutPanel> 控制項中的 <xref:System.Windows.Forms.Button> 控制項之 <xref:System.Windows.Forms.Control.Anchor%2A> 屬性值組合。  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/CS/TlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.AnchorExampleForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.AnchorExampleForm/VB/TlpAnchorExampleForm.vb#1)]  
  
## 編譯程式碼  
 這個範例需要：  
  
-   System、System.Data、System.Drawing 和 System.Windows.Forms 組件的參考。  
  
 如需從 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令列建置這個範例的相關資訊，請參閱[從命令列建置](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 或[使用 csc.exe 建置命令列](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。  您也可以透過將程式碼貼入新的專案，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中建置這個範例。  另請參閱[如何：使用 Visual Studio 編譯及執行完整的 Windows Form 程式碼範例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## 請參閱  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 [TableLayoutPanel 控制項](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)