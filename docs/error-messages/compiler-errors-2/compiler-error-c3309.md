---
title: 编译器错误 C3309
ms.date: 11/04/2016
f1_keywords:
- C3309
helpviewer_keywords:
- C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
ms.openlocfilehash: e66aa31982b018670684c8f12b05ba6f7347cd87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598141"
---
# <a name="compiler-error-c3309"></a>编译器错误 C3309

“macro_name”：模块名称不能是宏或关键字

将传递给模块特性的 name 属性的值不能为符号而必须是字符串文本，否则预处理器将无法展开。

下面的示例生成 C3309：

```
// C3309.cpp
#define NAME MyModule
[module(name="NAME")];   // C3309
// Try the following line instead
// [module(name="MyModule")];
[coclass]
class MyClass {
public:
   void MyFunc();
};

int main() {
}
```