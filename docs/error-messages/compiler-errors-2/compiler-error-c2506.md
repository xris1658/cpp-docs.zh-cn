---
title: 编译器错误 C2506
ms.date: 11/04/2016
f1_keywords:
- C2506
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
ms.openlocfilehash: 02f0a81204c4bc1c41111d32bae1c6946dee09ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575547"
---
# <a name="compiler-error-c2506"></a>编译器错误 C2506

member: __declspec(modifier) 不能应用于此符号

不能为托管类的静态成员声明每个进程或每个 appdomain。

有关更多信息，请参见 [appdomain](../../cpp/appdomain.md) 。

## <a name="example"></a>示例

下面的示例生成 C2506。

```
// C2506.cpp
// compile with: /clr /c
ref struct R {
   __declspec(process) static int n;   // C2506
   int o;   // OK
};
```