---
title: _CrtSetAllocHook
ms.date: 11/04/2016
apiname:
- _CrtSetAllocHook
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
apitype: DLLExport
f1_keywords:
- _CrtSetAllocHook
- CrtSetAllocHook
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: cfa466ec4bce6034c15a627ccab4ee4bb0ef8f5b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533674"
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook

通过挂钩到 C 运行时调试内存分配进程安装客户端定义的分配函数（仅限调试版本）。

## <a name="syntax"></a>语法

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>参数

*allocHook*<br/>
将新的客户端定义的分配函数挂钩到 C 运行时调试内存分配进程。

## <a name="return-value"></a>返回值

返回之前定义的分配挂钩函数，或**NULL**如果*allocHook*是**NULL**。

## <a name="remarks"></a>备注

**_CrtSetAllocHook** ，应用程序可以将其自己的分配函数挂钩到 C 运行时调试库内存分配进程。 因此，每次调用调试分配函数以分配、重新分配或释放内存块时都会触发对应用程序挂钩函数的调用。 **_CrtSetAllocHook**应用程序提供了一种简单方法用于测试应用程序如何处理内存不足的情况下，检查分配模式，并使他们有记录分配信息以更高版本的功能分析。 当[_DEBUG](../../c-runtime-library/debug.md)未定义，则调用 **_CrtSetAllocHook**在预处理过程中删除。

**_CrtSetAllocHook**函数安装中指定的新客户端定义的分配函数*allocHook*并返回之前定义的挂钩函数。 以下示例演示了客户端定义的分配挂钩如何构建原型：

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

**AllocType**参数指定的分配操作的类型 (**_HOOK_ALLOC**， **_HOOK_REALLOC**，以及 **_HOOK_FREE**)，触发对分配的挂钩函数的调用。 当触发分配类型是 **_HOOK_FREE**， *userData*是指向要释放的内存块的用户数据部分。 但是，当触发分配类型是 **_HOOK_ALLOC**或 **_HOOK_REALLOC**， *userData*是**NULL**因为内存块具有尚未分配。

*大小*指定的内存大小以字节为单位，阻止*blockType*指示内存块的类型*requestNumber*是对象分配序号的内存块，并且如果可用，*文件名*并**lineNumber**指定的源文件名和行号初始化之前触发分配操作的位置。

挂钩函数处理完成后，必须返回一个布尔值，该值将告诉主 C 运行时分配进程如何继续。 当挂钩函数想要主分配进程按继续如果从未被调用过挂钩函数，那么挂钩函数应返回 **，则返回 TRUE**。 这将导致执行原始触发分配操作。 使用该实现，挂钩函数可以收集和保存分配信息以用于以后分析，而不会干扰调试堆的当前分配操作或状态。

当挂钩函数想要主分配进程按继续如果调用触发分配操作和失败，那么挂钩函数应返回**FALSE**。 使用这个实现，挂钩函数可以模拟大范围的内存条件和调试堆状态，以测试应用程序如何处理每种情况。

若要清除挂钩函数，请将传递**NULL**到 **_CrtSetAllocHook**。

详细了解如何 **_CrtSetAllocHook**可以用于其他内存管理函数或如何编写您自己的客户端定义挂钩函数，请参阅[编写调试挂钩函数](/visualstudio/debugger/debug-hook-function-writing)。

> [!NOTE]
> **_CrtSetAllocHook**下，不支持 **/clr: pure**。 **/Clr: pure**并 **/clr: safe**编译器选项是在 Visual Studio 2015 中弃用并从 Visual Studio 2017 中删除。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

有关更多兼容性信息，请参阅 [兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

仅限 [C 运行时库](../../c-runtime-library/crt-library-features.md)的调试版本。

## <a name="example"></a>示例

有关如何使用的示例 **_CrtSetAllocHook**，请参阅[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)。

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>
