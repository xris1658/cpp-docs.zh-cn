---
title: includelib （c + + COM 属性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 4cfadc84b9131aa787323b4967ae9cfc4baabbcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570412"
---
# <a name="includelib-c"></a>includelib (C++)

导致要生成的.idl 文件中包含的.idl 或.h 文件。

## <a name="syntax"></a>语法

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>参数

*name.idl*<br/>
要生成的.idl 文件的一部分的.idl 文件的名称。

## <a name="remarks"></a>备注

**Includelib** c + + 属性会导致要包含在生成的.idl 文件中之后, 的.idl 或.h 文件`importlib`语句。

## <a name="example"></a>示例

下面的代码是.cpp 文件中所示：

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|任何位置|
|**可重复**|是|
|**必需的特性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[独立特性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)