---
title: 编译器错误 C2867
ms.date: 11/04/2016
f1_keywords:
- C2867
helpviewer_keywords:
- C2867
ms.assetid: 63be26b2-d9ab-4f3d-a8b7-981ce3e4d6b9
ms.openlocfilehash: 3c79fec9f52ea9451cea456dcc062af9bcbe9b3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602483"
---
# <a name="compiler-error-c2867"></a>编译器错误 C2867

identifier： 不是命名空间

一个`using`指令应用于命名空间以外的内容。

下面的示例生成 C2867:

```
// C2867.cpp
// compile with: /c
namespace N {
   class X {};
}
using namespace N::X;   // C2867
```