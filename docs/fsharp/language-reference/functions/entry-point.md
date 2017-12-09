---
title: "入口点 (F#)"
description: "了解如何设置为正式开始执行的可执行文件作为编译的 F # 程序的入口点。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 91455443-ff9d-4510-a7e9-1560bdcd0bb0
ms.openlocfilehash: 685fd4da67119aa5fcaaffd142a0a17c8f5dc7f6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="entry-point"></a><span data-ttu-id="336ef-104">入口点</span><span class="sxs-lookup"><span data-stu-id="336ef-104">Entry Point</span></span>

<span data-ttu-id="336ef-105">本主题介绍用于将入口点设置为 F # 程序的方法。</span><span class="sxs-lookup"><span data-stu-id="336ef-105">This topic describes the method that you use to set the entry point to an F# program.</span></span>


## <a name="syntax"></a><span data-ttu-id="336ef-106">语法</span><span class="sxs-lookup"><span data-stu-id="336ef-106">Syntax</span></span>

```fsharp
[<EntryPoint>]
let-function-binding
```

## <a name="remarks"></a><span data-ttu-id="336ef-107">备注</span><span class="sxs-lookup"><span data-stu-id="336ef-107">Remarks</span></span>
<span data-ttu-id="336ef-108">在上述语法中，*让函数绑定*是中的函数的定义`let`绑定。</span><span class="sxs-lookup"><span data-stu-id="336ef-108">In the previous syntax, *let-function-binding* is the definition of a function in a `let` binding.</span></span>

<span data-ttu-id="336ef-109">可执行文件正式开始执行时编译的程序入口点。</span><span class="sxs-lookup"><span data-stu-id="336ef-109">The entry point to a program that is compiled as an executable file is where execution formally starts.</span></span> <span data-ttu-id="336ef-110">通过应用指定的 F # 应用程序的入口点`EntryPoint`属性设为程序的`main`函数。</span><span class="sxs-lookup"><span data-stu-id="336ef-110">You specify the entry point to an F# application by applying the `EntryPoint` attribute to the program's `main` function.</span></span> <span data-ttu-id="336ef-111">此函数 (通过创建`let`绑定) 必须是最后一个已编译文件中的最后一个函数。</span><span class="sxs-lookup"><span data-stu-id="336ef-111">This function (created by using a `let` binding) must be the last function in the last compiled file.</span></span> <span data-ttu-id="336ef-112">最后编译的文件是项目中的最后一个文件或传递给命令行的最后一个文件。</span><span class="sxs-lookup"><span data-stu-id="336ef-112">The last compiled file is the last file in the project or the last file that is passed to the command line.</span></span>

<span data-ttu-id="336ef-113">入口点函数具有类型`string array -> int`。</span><span class="sxs-lookup"><span data-stu-id="336ef-113">The entry point function has type `string array -> int`.</span></span> <span data-ttu-id="336ef-114">在命令行上提供的自变量传递给`main`的字符串数组中的函数。</span><span class="sxs-lookup"><span data-stu-id="336ef-114">The arguments provided on the command line are passed to the `main` function in the array of strings.</span></span> <span data-ttu-id="336ef-115">数组的第一个元素是第一个自变量;可执行文件的名称未包含在数组中，因为它是在某些其他语言中。</span><span class="sxs-lookup"><span data-stu-id="336ef-115">The first element of the array is the first argument; the name of the executable file is not included in the array, as it is in some other languages.</span></span> <span data-ttu-id="336ef-116">返回值用作进程的退出代码。</span><span class="sxs-lookup"><span data-stu-id="336ef-116">The return value is used as the exit code for the process.</span></span> <span data-ttu-id="336ef-117">零通常指示成功;非零值指示错误。</span><span class="sxs-lookup"><span data-stu-id="336ef-117">Zero usually indicates success; nonzero values indicate an error.</span></span> <span data-ttu-id="336ef-118">没有特定的含义的返回代码则为非 0; 约定返回代码的意义进行了特定于应用程序。</span><span class="sxs-lookup"><span data-stu-id="336ef-118">There is no convention for the specific meaning of nonzero return codes; the meanings of the return codes are application-specific.</span></span>

<span data-ttu-id="336ef-119">下面的示例演示一个简单`main`函数。</span><span class="sxs-lookup"><span data-stu-id="336ef-119">The following example illustrates a simple `main` function.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/entry-point/snippet501.fs)]

<span data-ttu-id="336ef-120">使用命令行执行此代码时`EntryPoint.exe 1 2 3`，输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="336ef-120">When this code is executed with the command line `EntryPoint.exe 1 2 3`, the output is as follows.</span></span>

```console
Arguments passed to function : [|"1"; "2"; "3"|]
```

## <a name="implicit-entry-point"></a><span data-ttu-id="336ef-121">隐式的入口点</span><span class="sxs-lookup"><span data-stu-id="336ef-121">Implicit Entry Point</span></span>
<span data-ttu-id="336ef-122">当程序不具有**入口点**显式指示入口点，最后一个文件中的顶级绑定要编译的属性用作入口点。</span><span class="sxs-lookup"><span data-stu-id="336ef-122">When a program has no **EntryPoint** attribute that explicitly indicates the entry point, the top level bindings in the last file to be compiled are used as the entry point.</span></span>


## <a name="see-also"></a><span data-ttu-id="336ef-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="336ef-123">See Also</span></span>
[<span data-ttu-id="336ef-124">函数</span><span class="sxs-lookup"><span data-stu-id="336ef-124">Functions</span></span>](index.md)

[<span data-ttu-id="336ef-125">let 绑定</span><span class="sxs-lookup"><span data-stu-id="336ef-125">let Bindings</span></span>](let-bindings.md)