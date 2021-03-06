---
title: 编译器错误 C3287
ms.date: 11/04/2016
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: ab0b93aa1a74ea79515e24ef2b1e289cf0227dac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538669"
---
# <a name="compiler-error-c3287"></a>编译器错误 C3287

类型“type”（GetEnumerator 的返回类型）必须具有适当的公共 MoveNext 成员函数和公共的 Current 属性

用户定义的集合类必须包含对 `MoveNext` 和 `Current`的定义。

有关更多信息，请参见 [如何：使用 for each 循环访问用户定义集合](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) 。

## <a name="example"></a>示例

以下示例生成 C3287。

```
// C3287.cpp
// compile with: /clr
using namespace System;

ref struct R {
   bool MoveNext() {
      return true;
   }
   property Object^ Current {
      Object^ get() {
         Object ^ o = gcnew Object;
         return o;
      }
   }
};

ref struct R2 {
   R ^GetEnumerator() {
      R^ r = gcnew R;
      return r;
   }
};

ref struct T {};

ref struct T2 {
   T ^GetEnumerator() {
      T^ t = gcnew T;
      return t;
   }
};

int main() {
   for each (int i in gcnew T2) {}   // C3287
   for each (int i in gcnew R2) {}   // OK
}
```