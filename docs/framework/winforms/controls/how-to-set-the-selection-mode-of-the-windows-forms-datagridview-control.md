---
title: 如何：设置 Windows 窗体 DataGridView 控件的选择模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], modes in DataGridView control
- DataGridView control [Windows Forms], selection mode
- data grids [Windows Forms], selection mode
ms.assetid: 2f241643-7f82-4583-8757-03494f63b465
ms.openlocfilehash: 2e430dfb170943178f6db27c0bd2c1ef0f972882
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200553"
---
# <a name="how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control"></a>如何：设置 Windows 窗体 DataGridView 控件的选择模式
下面的代码示例演示如何配置<xref:System.Windows.Forms.DataGridView>控件，以便单击的任意位置的行自动选择整行，并且可以选择一次只有一个行。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#065)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#065](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#065)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
-   对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.MultiSelect%2A>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridViewSelectionMode>
- [Windows 窗体 DataGridView 控件的选项和剪贴板使用](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的选择模式](selection-modes-in-the-windows-forms-datagridview-control.md)
