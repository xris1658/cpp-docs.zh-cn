---
title: 编译器警告（等级 4）C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 3b82bfd1a1acff07a0fd47bbd2abfb08178a74c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605356"
---
# <a name="compiler-warning-level-4-c4125"></a>编译器警告（等级 4）C4125

十进制数字终止八进制转义序列

编译器未用十进制数求八进制数，并假定十进制数字是一个字符。

## <a name="example"></a>示例

```
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

如果数字 9 作为一个字符，请如下更正示例：

```
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```