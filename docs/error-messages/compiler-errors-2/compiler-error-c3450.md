---
title: 编译器错误 C3450
ms.date: 11/04/2016
f1_keywords:
- C3450
helpviewer_keywords:
- C3450
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
ms.openlocfilehash: bedf78ef1cea9f17903fd05f9440c6baa69f7333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481232"
---
# <a name="compiler-error-c3450"></a>编译器错误 C3450

“type”：不是特性；不能指定 [System::AttributeUsageAttribute] 或 [Windows::Foundation::Metadata::AttributeUsageAttribute]

用户定义的托管特性必须继承自 <xref:System.ComponentModel.AttributeCollection.%23ctor%2A>。 Windows 运行时特性必须在 `Windows::Foundation::Metadata` 命名空间中定义。

有关详细信息，请参阅 [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例将生成 C3450，并演示如何修复此错误。

```
// C3450.cpp
// compile with: /clr
// C3450 expected
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref struct AtClass {
   AtClass(Type ^) {}
};

[attribute(AttributeTargets::All)]
ref struct AtClass2 {
   AtClass2() {}
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
// Delete the following line to resolve.
ref class B {};
// Uncomment the following line to resolve.
// ref class B : Attribute {};
```