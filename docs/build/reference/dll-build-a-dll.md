---
title: /DLL（生成 DLL）
ms.date: 11/04/2016
f1_keywords:
- /dll
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
ms.openlocfilehash: 71696e4ffae91ed1fa8a13e69e75523ce66e8361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546326"
---
# <a name="dll-build-a-dll"></a>/DLL（生成 DLL）

```
/DLL
```

## <a name="remarks"></a>备注

/DLL 选项生成 DLL 作为主输出文件。 DLL 通常包含可由其他程序的导出。 有三种方法用于指定导出，建议使用的顺序依次列出：

1. [__declspec （dllexport)](../../cpp/dllexport-dllimport.md)中的源代码

1. [导出](../../build/reference/exports.md).def 文件语句

1. [/Export](../../build/reference/export-exports-a-function.md) LINK 命令中的规范

程序可以使用多个方法。

另一种方法来生成 DLL 是使用**库**模块定义语句。 /BASE 和 /DLL 选项一起构成了等效于**库**语句。

未指定此选项在开发环境中;此选项适用于仅在命令行上使用。 使用应用程序向导创建 DLL 项目时设置此选项。

请注意，是否创建.dll 之前，可以在初始步骤中，创建导入库，则必须通过同一组对象文件时生成.dll 文件，为通过生成导入库时。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[设置 Visual c + + 项目属性](../../ide/working-with-project-properties.md)。

1. 单击**配置属性**文件夹。

1. 单击**常规**属性页。

1. 修改**配置类型**属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>。

## <a name="see-also"></a>请参阅

[设置链接器选项](../../build/reference/setting-linker-options.md)<br/>
[链接器选项](../../build/reference/linker-options.md)