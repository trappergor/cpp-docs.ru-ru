---
title: Классы поддержки Windows (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: 5880fd970d885da84edd94f9f2c7a47ec326ebe1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195492"
---
# <a name="windows-support-classes"></a>Классы поддержки Windows

Следующие классы обеспечивают поддержку windows.

- [_U_MENUorID](../atl/reference/u-menuorid-class.md) предоставляет оболочки для `CreateWindow` и `CreateWindowEx`.

- [CWindow](../atl/reference/cwindow-class.md) содержит методы для управления окном. `CWindow` — это базовый класс для `CWindowImpl`, `CDialogImpl` и `CContainedWindow`.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) реализует окно, в зависимости от нового класса окна. Также позволяет подкласс или суперкласса окна.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) реализует диалоговое окно.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) реализует диалоговое окно (модальное или немодальное), на котором размещены элементы управления ActiveX.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) реализует диалоговое окно (модальное или немодальное) с базовыми функциями.

- [CAxWindow](../atl/reference/caxwindow-class.md) управляет окном, в котором размещается элемент управления ActiveX.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) содержит методы для работы окно, которое размещает элемент ActiveX, а также поддержку размещения Лицензированные элементы управления ActiveX.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) реализует окно, содержатся внутри другого объекта.

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) управляет данными нового класса окна.

- [CDynamicChain](../atl/reference/cdynamicchain-class.md) поддержка динамического объединения схемы сообщений.

- [CMessageMap](../atl/reference/cmessagemap-class.md) позволяет объекту предоставлять его сообщения сопоставляется с другими объектами.

- [CWinTraits](../atl/reference/cwintraits-class.md) предлагает простой способ стандартизации признаки объекта ATL окна.

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) предоставляет значения по умолчанию для стилей окна и расширенные стили, используемые для создания окна. Эти значения добавляются с помощью оператора логического или, для значений, предоставленных во время создания окна.

## <a name="related-articles"></a>Связанные статьи

[Классы окон ATL](../atl/atl-window-classes.md)

[Учебник по ATL](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)<br/>
[Макросы схемы сообщений](../atl/reference/message-map-macros-atl.md)<br/>
[Макросы класса окна](../atl/reference/window-class-macros.md)
