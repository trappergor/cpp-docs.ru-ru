---
title: Точки входа интерфейса COM
ms.date: 11/04/2016
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: 3c7b0067e66dfa8bc6f52bcd67637370f8c9a758
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288078"
---
# <a name="com-interface-entry-points"></a>Точки входа интерфейса COM

Для функций-членов интерфейса COM используйте [METHOD_PROLOGUE](com-interface-entry-points.md#method_prologue) макрос для поддержания соответствующего глобального состояния, при вызове методов экспортированного интерфейса.

Как правило, функции-члены интерфейсов, реализуемый `CCmdTarget`-производных объектов уже используйте этот макрос для предоставления автоматическую инициализацию `pThis` указатель. Пример:

[!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/cpp/com-interface-entry-points_1.cpp)]

Дополнительные сведения см. в разделе [технические 38 Примечание](../mfc/tn038-mfc-ole-iunknown-implementation.md) на MFC/OLE `IUnknown` реализации.

`METHOD_PROLOGUE` Макрос определяется как:

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

Часть макрос, касающиеся управления глобальное состояние является:

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

В этом выражении *m_pModuleState* предполагается, что переменную-член края содержащего его объекта. Она реализуется `CCmdTarget` базового класса и инициализируется с соответствующим значением, `COleObjectFactory`, при создании экземпляра объекта.

## <a name="see-also"></a>См. также

[Управление данными состояния модулей MFC](../mfc/managing-the-state-data-of-mfc-modules.md)
