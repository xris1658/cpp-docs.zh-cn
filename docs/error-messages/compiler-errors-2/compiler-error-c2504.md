---
title: 编译器错误 C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 8f428699aa14cbd1f021a57ed8dcabefa8b24c16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444386"
---
# <a name="compiler-error-c2504"></a>编译器错误 C2504

class： 未定义基类

声明类的基类，但是永远不会定义。  可能的原因：

1. 缺少包含文件。

1. 使用未声明外部基类[extern](../../cpp/using-extern-to-specify-linkage.md)。

下面的示例生成 C2504:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

还行

```
class C{};
class D : public C {};
```