---
title: MFC 应用程序体系结构类
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
ms.openlocfilehash: 3287ac31744506720f1c5c1080a6225311f0e3a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512750"
---
# <a name="mfc-application-architecture-classes"></a>MFC 应用程序体系结构类

此类别的类构成框架应用程序的体系结构。 它们提供大部分应用程序常见的功能。 填充框架以添加应用程序特定功能。 通常，您通过从体系结构类派生新的类，然后添加新成员或重写现有成员函数来实现。

[应用程序向导](../mfc/reference/mfc-application-wizard.md)生成多种类型的应用程序，它们都通过不同的方式使用应用程序框架。 SDI（单文档界面）和 MDI（多文档界面）应用程序将充分利用称为文档/视图体系结构的框架的一部分。 其他类型的应用程序（如基于对话框的应用程序、基于窗体的应用程序和 DLL）仅使用部分文档/视图体系结构功能。

文档/视图应用程序包含一个或多个文档、视图和框架窗口集。 文档模板对象将每个文档/视图/框架集的类关联起来。

虽然您在 MFC 应用程序中不必使用文档/视图体系结构，但这样做有很多好处。 MFC OLE 容器和服务器支持基于文档/视图体系结构，如对打印和打印预览的支持。

所有 MFC 应用程序都具有至少两个对象： 应用程序对象派生自[CWinApp](../mfc/reference/cwinapp-class.md)，和某种形式的主窗口对象 （一般间接） 派生自[CWnd](../mfc/reference/cwnd-class.md)。 (大多数情况下，主窗口派生自[CFrameWnd](../mfc/reference/cframewnd-class.md)， [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md)，或[CDialog](../mfc/reference/cdialog-class.md)，所有这些派生自`CWnd`。)

使用文档/视图体系结构的应用程序包含其他对象。 主要对象有：

- 应用程序对象派生自类[CWinApp](../mfc/reference/cwinapp-class.md)，如前面所述。

- 一个或多个文档类对象派生自类[CDocument](../mfc/reference/cdocument-class.md)。 文档类对象负责视图中操作数据的内部表示。 它们可能与数据文件关联。

- 一个或多个视图对象派生自类[CView](../mfc/reference/cview-class.md)。 每个视图都是附加到文档并与框架窗口关联的一个窗口。 视图显示和操作文档类对象中包含的数据。

文档/视图应用程序还包含框架窗口 (派生自[CFrameWnd](../mfc/reference/cframewnd-class.md)) 和文档模板 (派生自[CDocTemplate](../mfc/reference/cdoctemplate-class.md))。

## <a name="see-also"></a>请参阅

[类概述](../mfc/class-library-overview.md)

