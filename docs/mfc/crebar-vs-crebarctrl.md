---
title: CReBar 与CReBarCtrl
ms.date: 11/04/2016
f1_keywords:
- CReBar
- CReBarCtrl
helpviewer_keywords:
- CReBar class [MFC], vs. CReBarCtrl
- rebar controls [MFC], CReBarCtrl class [MFC]
- GetReBarCtrl class [MFC]
ms.assetid: 7f9c1d7e-5d5f-4956-843c-69ed3df688d0
ms.openlocfilehash: 49a1528e52d140a673d4035c55394ded3656652f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641401"
---
# <a name="crebar-vs-crebarctrl"></a>CReBar 与CReBarCtrl

MFC 提供了两个类来创建 rebar: [CReBar](../mfc/reference/crebar-class.md)并[CReBarCtrl](../mfc/reference/crebarctrl-class.md) （其包装 Windows 公共控件 API）。 `CReBar` 提供的所有 rebar 常用控制，功能，还可以为您处理许多必需的常用控制设置和结构。

`CReBarCtrl` 是 Win32 rebar 控制的包装器类，因此如果您不打算将 rebar 集成到 MFC 体系结构中，则这可能更易于实现。 如果您计划使用 `CReBarCtrl` 并计划将 rebar 集成到 MFC 体系结构中，则必须额外注意将 rebar 控制操作传送到 MFC。 此通信并不困难;但是，它是在使用时是不需要的额外工作`CReBar`。

Visual C++ 提供了两种利用 rebar 常用控制的方式。

- 创建 rebar 使用`CReBar`，然后调用[crebar:: Getrebarctrl](../mfc/reference/crebar-class.md#getrebarctrl)若要访问`CReBarCtrl`成员函数。

    > [!NOTE]
    >  `CReBar::GetReBarCtrl` 是一个内联成员函数，将强制转换**这**rebar 对象的指针。 这意味着，函数调用在运行时没有开销。

- 创建 rebar 使用[CReBarCtrl](../mfc/reference/crebarctrl-class.md)的构造函数。

任一方法都将为您提供对 rebar 控制的成员函数的访问权限。 当您调用 `CReBar::GetReBarCtrl` 时，它将返回对 `CReBarCtrl` 对象的引用，以便您可以使用成员函数集。 请参阅[CReBar](../mfc/reference/crebar-class.md)信息构造和创建 rebar 使用`CReBar`。

## <a name="see-also"></a>请参阅

[使用 CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)

