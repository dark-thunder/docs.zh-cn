---
title: 如何：使用设计器向 Windows 窗体 ListView 控件添加列
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 83ea97b0961d158a1f3ab7a77ad2aa93732c17b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528390"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器向 Windows 窗体 ListView 控件添加列
Windows 窗体<xref:System.Windows.Forms.ListView>控件可以显示多个列进行每个列表项时在**详细信息**视图。 可以使用列以显示多种类型的每个列表项的相关信息。 例如，文件的列表，无法显示文件名、 文件类型、 大小和上次修改文件的日期。 有关创建后填充各列的信息，请参阅[如何： 在使用 Windows 窗体 ListView 控件的列中显示子项](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ListView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-columns-in-the-designer"></a>在设计器中添加列  
  
1.  在**属性**窗口中，设置控件的<xref:System.Windows.Forms.ListView.View%2A>属性<xref:System.Windows.Forms.View.Details>。  
  
2.  在**属性**窗口中，单击**省略号**按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.ListView.Columns%2A>属性。  
  
     **ColumnHeader 集合编辑器**显示。  
  
3.  使用**添加**按钮以添加新列。 然后，你可以选择列标题，并设置其文本 （列的标题）、 文本对齐方式和宽度。  
  
## <a name="see-also"></a>请参阅  
 [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 ListView 控件添加和删除项](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [如何：使用 Windows 窗体 ListView 控件在列中显示子项](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [如何：显示 Windows 窗体 ListView 控件的图标](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
