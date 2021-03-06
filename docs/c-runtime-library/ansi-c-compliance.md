---
title: ANSI C 遵从性
ms.date: 11/04/2016
f1_keywords:
- Ansi
helpviewer_keywords:
- underscores, leading
- compatibility [C++], ANSI C
- compliance with ANSI C
- conventions [C++], Microsoft extensions
- underscores
- naming conventions [C++], Microsoft library
- ANSI [C++], C standard
- Microsoft extensions naming conventions
ms.assetid: 6be271bf-eecf-491a-a928-0ee2dd60e3b9
ms.openlocfilehash: c84485fdd06bc9264241cb37aa3c6b2fb29d9322
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620748"
---
# <a name="ansi-c-compliance"></a>ANSI C 遵从性

在运行时系统（如函数、宏、常量、变量和类型定义）中，所有 Microsoft 专用标识符的命名规则均符合 ANSI 标准。 在本文档中，任何符合 ANSI/ISO C 标准的运行时函数都将标记为与 ANSI 兼容。 符合 ANSI 标准的应用程序应仅使用这些与 ANSI 兼容的函数。

Microsoft 专用函数和全局变量的名称均以一个下划线开头。 这些名称只能在您的代码范围内进行本地重写。 例如，当您包括 Microsoft 运行时标头文件时，仍然可以通过声明同名的局部变量，在本地重写名为 `_open` 的 Microsoft 专用函数。 但是，不可将此名称用于您自己的全局函数或全局变量。

Microsoft 专用的宏和清单常量的名称均以两个下划线（或一个后面紧跟一个大写字母的前导下划线）开头。 这些标识符的范围是绝对的。 例如，不可将 Microsoft 专用的标识符 _UPPER 用于此目的。

## <a name="see-also"></a>请参阅

[兼容性](../c-runtime-library/compatibility.md)