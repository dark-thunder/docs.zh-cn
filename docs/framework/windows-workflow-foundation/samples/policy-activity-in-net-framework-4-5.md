---
title: .NET Framework 4.5 中的策略活动
ms.date: 03/30/2017
ms.assetid: 8e375e0c-d7c1-4d69-88ab-36d52db0aa7e
ms.openlocfilehash: 52f0cdd3714367598c83f72e2a8203c2ae27eb4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="policy-activity-in-net-framework-45"></a>.NET Framework 4.5 中的策略活动
Policy4 活动允许 Windows Workflow Foundation 中[!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)](WF 3.5)<xref:System.Workflow.Activities.Rules.RuleSet>对象用于在 Windows Workflow Foundation 中[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)](WF 4.5) 直接通过 WF 3.5 中附带的规则引擎。 通过使用此活动，可以创建和执行 WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>。 有关 Windows Workflow Foundation 的一部分包含的 WF 3.5 规则引擎的详细信息，请阅读 Windows Workflow Foundation 规则引擎简介。 有关迁移的详细信息中的 WF 规则[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]，请阅读[迁移指南](../../../../docs/framework/windows-workflow-foundation/migration-guidance.md)。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-Policy4`  
  
## <a name="projects-in-this-sample"></a>此示例中的项目  
  
|项目名称|描述|主要文件|  
|------------------|-----------------|----------------|  
|Policy4|包含 Policy4 活动及其 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 设计器。|**Policy4.cs**: Policy4 活动定义。<br /><br /> **PolicyDesigner.xaml**: Policy4 活动的自定义设计器。 它使用的规则编辑器 ([RuleSetDialog 类](http://go.microsoft.com/fwlink/?LinkId=150378)) 从[!INCLUDE[wf1](../../../../includes/wf1-md.md)]规则引擎。|  
|ImperativeCodeClientSample|一个示例客户端应用程序，此应用程序使用命令性 C# 代码（未使用任何 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 设计器）来配置和运行使用 Policy4 应用程序的工作流。|**ApplyDiscount.rules**： 使用文件[!INCLUDE[wf1](../../../../includes/wf1-md.md)]规则定义。<br /><br /> **Order.cs**： 表示客户订单的类型。 规则适用于此类型的对象。<br /><br /> **Program.cs**： 配置和运行具有 Policy4 活动要应用于 Order 对象的实例的 ApplyDiscount.rules 中定义的规则的工作流。<br /><br /> **App.config**： 带有规则文件的路径的配置文件。|  
|DesignerClientSample|一个示例客户端应用程序，此应用程序在 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 设计器中配置和运行使用 Policy4 应用程序的工作流。|**Sequence1.xaml**： 使用 Policy4 活动执行规则计算的顺序工作流。<br /><br /> `Program.cs`：运行 Sequence1.xaml 中定义的工作流的实例。|  
  
## <a name="the-policy4-activity"></a>Policy4 活动  
 Policy4 活动是一个从 <xref:System.Activities.NativeActivity%601> 派生的类，它允许工作流执行 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] RuleSets。 下面的代码示例是活动的公共 OM 的简化定义。  
  
```csharp  
public class Policy4Activity<TResult>: NativeActivity<TResult>  
{  
    public RuleSet RuleSet  
  
    [IsRequired]  
    public InArgument Input  
  
    public OutArgument<ValidationErrorCollection> ValidationErrors  
}  
```  
  
|属性|描述|  
|--------------|-----------------|  
|RuleSet|WF [RuleSet 类](http://go.microsoft.com/fwlink/?LinkId=150379)执行活动时要计算的.NET Framework 3.5。|  
|TargetObject|依据对象中的规则[RuleSet 类](http://go.microsoft.com/fwlink/?LinkId=150379)进行评估。|  
|ValidationError|返回的验证错误的列表[!INCLUDE[wf1](../../../../includes/wf1-md.md)]验证时的.NET Framework 3.5 规则引擎[RuleSet 类](http://go.microsoft.com/fwlink/?LinkId=150379)对目标对象之前执行。|  
  
## <a name="policy4-activity-designer"></a>Policy4 活动设计器  
 Policy4 设计器增加了一项功能，利用此功能，无需编写代码即可配置 Policy4 活动。 生成解决方案之后, 它可在工具箱的部分中**Microsoft.Samples.Activities.Rules**。  
  
 利用 WF 设计器可配置目标对象和 RuleSet。 当**编辑 RuleSet**单击按钮时，WF [RuleSetDialog 类](http://go.microsoft.com/fwlink/?LinkId=150378)为[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]显示。 此对话框是重新承载的 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 规则编辑器。 使用该编辑器可创建和编辑 Policy4 活动执行的规则。  
  
## <a name="using-this-sample"></a>使用此示例  
 无需进行特殊设置即可运行此示例。 只需在 Visual Studio 中打开解决方案，然后按 F5 即可运行应用程序。  
  
 此示例包含两个客户端应用程序，即 ImperativeCodeClientSample 和 DesignerClientSample。 ImperativeCodeClientSample 客户端演示如何使用 C# 命令性代码来配置和运行 Policy4 活动。 DesignerClientSample 演示如何使用设计器配置和运行 Policy4 活动。  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>运行 ImperativeCodeClientSample 客户端应用程序  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 Policy4Sample.sln 解决方案文件。  
  
2.  在**解决方案资源管理器**，右键单击**ImperativeCodeClientSample**项目，然后选择**设为启动项目**。  
  
3.  若要运行项目，请按 Ctrl+F5。  
  
#### <a name="to-run-the-imperativecodeclientsample-client-application"></a>运行 ImperativeCodeClientSample 客户端应用程序  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 Policy4Sample.sln 解决方案文件。  
  
2.  在**解决方案资源管理器**，右键单击**DesignerClientSample**项目。  
  
    -   选择**设为启动项目**。  
  
3.  若要编译项目，请按 Ctrl+Shift+B。  
  
4.  若要运行项目，请按 Ctrl+F5。