---
title: Точки входа интерфейса COM
ms.date: 03/27/2019
helpviewer_keywords:
- entry points, COM interfaces
- state management, OLE/COM interfaces
- MFC COM, COM interface entry points
- OLE, interface entry points
- MFC, managing state data
- COM interfaces, entry points
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
ms.openlocfilehash: 132dd7394119081dcaeb098c2088782ff5d40ae4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619341"
---
# <a name="com-interface-entry-points"></a>Точки входа интерфейса COM

Для функций-членов интерфейса COM используйте `METHOD_PROLOGUE` макрос для поддержания правильного глобального состояния при вызове методов экспортированного интерфейса.

Как правило, функции-члены интерфейсов, реализованных производными от классами `CCmdTarget` объектами, уже используют этот макрос для автоматической инициализации `pThis` указателя. Пример.

[!code-cpp[NVC_MFCConnectionPoints#5](codesnippet/cpp/com-interface-entry-points_1.cpp)]

Дополнительные сведения см. в [техническом примечании 38](tn038-mfc-ole-iunknown-implementation.md) по реализации MFC/OLE `IUnknown` .

`METHOD_PROLOGUE`Макрос определяется следующим образом:

```cpp
#define METHOD_PROLOGUE(theClass, localClass) \
    theClass* pThis = \
    ((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \
    AFX_MANAGE_STATE(pThis->m_pModuleState) \
```

Часть макроса, относящаяся к управлению глобальным состоянием, — это:

`AFX_MANAGE_STATE( pThis->m_pModuleState )`

В этом выражении *m_pModuleState* предполагается как переменная-член содержащего его объекта. Он реализуется `CCmdTarget` базовым классом и инициализируется соответствующим значением в `COleObjectFactory` , когда создается экземпляр объекта.

## <a name="see-also"></a>См. также раздел

[Управление данными состояния модулей MFC](managing-the-state-data-of-mfc-modules.md)
