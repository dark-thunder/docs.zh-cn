---
title: "IMetaDataAssemblyImport::FindExportedTypeByName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.FindExportedTypeByName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b7ef0e09cb5a44e612e545fc4ee7278c2d128174
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a><span data-ttu-id="2c937-102">IMetaDataAssemblyImport::FindExportedTypeByName 方法</span><span class="sxs-lookup"><span data-stu-id="2c937-102">IMetaDataAssemblyImport::FindExportedTypeByName Method</span></span>
<span data-ttu-id="2c937-103">获取一个指向导出的类型，在给定其名称和封闭类型。</span><span class="sxs-lookup"><span data-stu-id="2c937-103">Gets a pointer to an exported type, given its name and enclosing type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c937-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c937-104">Syntax</span></span>  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c937-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c937-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="2c937-106">[in]导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="2c937-106">[in] The name of the exported type.</span></span>  
  
 `mdtExportedType`  
 <span data-ttu-id="2c937-107">[in]导出的类型的封闭类元数据标记。</span><span class="sxs-lookup"><span data-stu-id="2c937-107">[in] The metadata token for the enclosing class of the exported type.</span></span> <span data-ttu-id="2c937-108">此值是`mdExportedTypeNil`如果请求的导出类型不是嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="2c937-108">This value is `mdExportedTypeNil` if the requested exported type is not a nested type.</span></span>  
  
 `ptkExportedType`  
 <span data-ttu-id="2c937-109">[out]指向的指针`mdExportedType`表示导出的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="2c937-109">[out] A pointer to the `mdExportedType` token that represents the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c937-110">备注</span><span class="sxs-lookup"><span data-stu-id="2c937-110">Remarks</span></span>  
 <span data-ttu-id="2c937-111">`FindExportedTypeByName`方法使用由解析的引用的公共语言运行时的标准规则。</span><span class="sxs-lookup"><span data-stu-id="2c937-111">The `FindExportedTypeByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c937-112">要求</span><span class="sxs-lookup"><span data-stu-id="2c937-112">Requirements</span></span>  
 <span data-ttu-id="2c937-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c937-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c937-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c937-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c937-115">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2c937-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c937-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c937-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c937-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c937-117">See Also</span></span>  
 [<span data-ttu-id="2c937-118">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="2c937-118">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [<span data-ttu-id="2c937-119">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="2c937-119">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)