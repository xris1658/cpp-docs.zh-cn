---
title: ATL 全局变量
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 4f98b31d2454b7c6e903e5b5b87bceb4ddcb6961
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498314"
---
# <a name="atl-global-variables"></a>ATL 全局变量

## <a name="patlmodule"></a>_pAtlModule

存储指向当前模块的全局变量。

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>备注

此全局变量的方法可以用于提供 （现在已过时） 类 CComModule Visual c + + 6.0 中提供的功能。

### <a name="example"></a>示例

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>要求

**标头：** atlbase.h
