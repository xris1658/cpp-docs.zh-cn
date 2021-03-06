---
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 9367457a8e7f6be1f372244f8288a994eb777071
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613780"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

此选项可显示的 Dll 列表 (静态链接并[延迟加载](../../build/reference/linker-support-for-delay-loaded-dlls.md)) 的导入到一个可执行文件或 DLL 和的各个导入从每个这些 Dll。

可选`file`规范允许您指定将显示仅限于该 DLL 的导入。 例如：

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>备注

通过此选项显示的输出是类似于[/exports](../../build/reference/dash-exports.md)输出。

仅[/HEADERS](../../build/reference/headers.md) DUMPBIN 选项仅适用于使用产生的文件[/GL](../../build/reference/gl-whole-program-optimization.md)编译器选项。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](../../build/reference/dumpbin-options.md)