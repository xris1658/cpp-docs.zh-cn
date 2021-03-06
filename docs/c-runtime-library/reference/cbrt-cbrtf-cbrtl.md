---
title: cbrt、cbrtf、cbrtl
ms.date: 04/05/2018
apiname:
- cbrt
- cbrtf
- cbrtl
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- cbrtl
- cbrt
- cbrtf
helpviewer_keywords:
- cbrtl function
- cbrtf function
- cbrt function
ms.assetid: ab51d916-3db2-4beb-b46a-28b4062cd33f
ms.openlocfilehash: c395a063cfa07cdfb7e841f19bc64fb1c57ca796
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505529"
---
# <a name="cbrt-cbrtf-cbrtl"></a>cbrt、cbrtf、cbrtl

计算立方根。

## <a name="syntax"></a>语法

```C
double cbrt(
   double x
);
float cbrt(
   float x
);  // C++ only
long double cbrt(
   long double x
);  // C++ only
float cbrtf(
   float x
);
long double cbrtl(
   long double x
);
```

### <a name="parameters"></a>参数

*x*<br/>
浮点值

## <a name="return-value"></a>返回值

**Cbrt**函数返回的多维数据集根目录*x*。

|输入|SEH 异常|**_matherr**异常|
|-----------|-------------------|--------------------------|
|± ∞、QNAN、IND|无|无|

## <a name="remarks"></a>备注

由于 c + + 允许重载，可以调用的重载**cbrt**采用**float**或**长** **double**类型。 在 C 程序中， **cbrt**始终采用并返回**double**。

## <a name="requirements"></a>要求

|函数|C 标头|C++ 标头|
|--------------|--------------|------------------|
|**cbrt**， **cbrtf**， **cbrtl**|\<math.h>|\<cmath>|

有关其他兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

```C
// crt_cbrt.c
// Compile using: cl /W4 crt_cbrt.c
// This program calculates a cube root.

#include <math.h>
#include <stdio.h>

int main( void )
{
   double question = -64.64;
   double answer;

   answer = cbrt(question);
   printf("The cube root of %.2f is %.6f\n", question, answer);
}
```

```Output
The cube root of -64.64 is -4.013289
```

## <a name="see-also"></a>请参阅

[浮点支持](../../c-runtime-library/floating-point-support.md)<br/>
[exp、expf、expl](exp-expf.md)<br/>
[log、logf、log10、log10f](log-logf-log10-log10f.md)<br/>
[pow、powf、powl](pow-powf-powl.md)<br/>
