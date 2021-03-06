---
title: 语法摘要的定义
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
ms.openlocfilehash: 133000c0cc8ef636a3f9752d2f6fc7f1934bd831
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521120"
---
# <a name="definitions-for-the-grammar-summary"></a>语法摘要的定义

终止符是语法定义中的终结点。 不提供其他解决方法。 终止符包括保留字和用户定义的标识符的集。

非终止符是语法中的占位符。 它们中的大多数是在此语法摘要中的其他位置定义的。 定义可是递归的。 在中定义以下非终止符[词法约定](../cpp/lexical-conventions.md)一部分*c + + 语言参考*:

`constant`*常数表达式*，*标识符*，*关键字*， `operator`， `punctuator`

可选组件由带下标的 <sub>opt</sub> 指示。 例如，下面指示包含在大括号中的可选表达式：

**{** *expression*<sub>opt</sub> **}**

## <a name="see-also"></a>请参阅

[语法摘要 (C/C++)](../preprocessor/grammar-summary-c-cpp.md)