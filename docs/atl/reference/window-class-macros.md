---
title: Макрос класса окон
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: 18c0912c506bc52421b18d36346204b557c0fc5c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325734"
---
# <a name="window-class-macros"></a>Макрос класса окон

Эти макросы определяют утилиты класса окон.

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|Позволяет указать название нового класса окон.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Визуальная студия 2017) Позволяет указать имя нового класса окон и класс оконного, который будет использовать процедура окна нового класса.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Позволяет указать имя существующего класса окон, на котором будет базироваться новый класс окон.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Позволяет указать параметры класса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

## <a name="declare_wnd_class"></a><a name="declare_wnd_class"></a>DECLARE_WND_CLASS

Позволяет указать название нового класса окон. Поместите этот макрос в класс управления ATL ActiveX.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
(в) Название нового класса окон. Если NULL, ATL будет генерировать имя класса окна.

### <a name="remarks"></a>Remarks

Если вы используете опцию /разрешительно-компилятор, то DECLARE_WND_CLASS вызовет ошибку компилятора; вместо этого используйте DECLARE_WND_CLASS2.

DECLARE_WND_CLASS позволяет указать название нового класса окон, информация которого будет управляться [CWndClassInfo](cwndclassinfo-class.md). DECLARE_WND_CLASS определяет новый класс окон, реализуя следующую статическую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS определяет следующие стили для нового окна:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS также определяет цвет фона окна по умолчанию. Используйте [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) макрос, чтобы обеспечить свои собственные стили и цвет фона.

[CWindowImpl](cwindowimpl-class.md) использует DECLARE_WND_CLASS макрос для создания окна на основе нового класса окон. Чтобы переопределить это поведение, используйте [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) макрос или предоставьте собственную реализацию функции [GetWndClassInfo.](cwindowimpl-class.md#getwndclassinfo)

Для получения дополнительной информации об использовании [ATL Window Classes](../../atl/atl-window-classes.md)окон в ATL, см.

## <a name="declare_wnd_class2"></a><a name="declare_wnd_class2"></a>DECLARE_WND_CLASS2

(Визуальная студия 2017) Как и DECLARE_WND_CLASS, но с дополнительным параметром, который позволяет избежать ошибки зависимого имени при компиляции с /разрешительно-опционом.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
(в) Название нового класса окон. Если NULL, ATL будет генерировать имя класса окна.

*Прилагающийкласс*<br/>
(в) Название класса окон, которое закрывает новый класс окон. Не может быть NULL.

### <a name="remarks"></a>Remarks

Если вы используете /разрешительно-опцию, то DECLARE_WND_CLASS вызовет ошибку компиляции, поскольку она содержит зависимое имя. DECLARE_WND_CLASS2 требует, чтобы вы явно назвали класс, в который используется этот макрос, и не вызывает ошибку под /разрешительным флагом.
В противном случае этот макрос идентичен [DECLARE_WND_CLASS.](#declare_wnd_class)

## <a name="declare_wnd_superclass"></a><a name="declare_wnd_superclass"></a>DECLARE_WND_SUPERCLASS

Позволяет указать параметры класса. Поместите этот макрос в класс управления ATL ActiveX.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
(в) Название класса окон, который будет суперкласс *OrigWndClassName*. Если NULL, ATL будет генерировать имя класса окна.

*OrigWndClassName*<br/>
(в) Название существующего класса окон.

### <a name="remarks"></a>Remarks

Этот макрос позволяет указать имя класса окон, который будет классифицировать существующий класс окон. [CWndClassInfo](cwndclassinfo-class.md) управляет информацией суперкласса.

DECLARE_WND_SUPERCLASS реализует следующую статическую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

По умолчанию [CWindowImpl](cwindowimpl-class.md) использует [DECLARE_WND_CLASS](#declare_wnd_class) макрос для создания окна на основе нового класса окон. Указывая DECLARE_WND_SUPERCLASS макрос `CWindowImpl`в классе, полученном, класс окон будет основываться на существующем классе, но будет использовать процедуру окна. Этот метод называется суперклассированием.

Помимо использования DECLARE_WND_CLASS и DECLARE_WND_SUPERCLASS макросов, вы можете переопределить функцию [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) с вашей собственной реализацией.

Для получения дополнительной информации об использовании [ATL Window Classes](../../atl/atl-window-classes.md)окон в ATL, см.

## <a name="declare_wnd_class_ex"></a><a name="declare_wnd_class_ex"></a>DECLARE_WND_CLASS_EX

Позволяет указать имя существующего класса окон, на котором будет базироваться новый класс окон. Поместите этот макрос в класс управления ATL ActiveX.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
(в) Название нового класса окон. Если NULL, ATL будет генерировать имя класса окна.

*Стиль*<br/>
(в) Стиль окна.

*bkgnd*<br/>
(в) Цвет фона окна.

### <a name="remarks"></a>Remarks

Этот макрос позволяет указать параметры класса нового класса окон, информация о котором будет управляться [CWndClassInfo.](cwndclassinfo-class.md) DECLARE_WND_CLASS_EX определяет новый класс окон, реализуя следующую статическую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Если вы хотите использовать стили по умолчанию и цвет фона, используйте [DECLARE_WND_CLASS](#declare_wnd_class) макрос. Для получения дополнительной информации об использовании [ATL Window Classes](../../atl/atl-window-classes.md)окон в ATL, см.

## <a name="see-also"></a>См. также раздел

[Макросы](atl-macros.md)
