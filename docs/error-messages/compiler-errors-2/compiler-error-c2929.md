---
title: 编译器错误 C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: fe2a56f7722c70c11e980fb6ee59230ffd056c5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658804"
---
# <a name="compiler-error-c2929"></a>编译器错误 C2929

“identifier”：显式实例化；无法显式强制和取消模板类成员的实例化

不能在防止标识符实例化的同时对其进行显式实例化。

下面的示例生成 C2929：

```
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```