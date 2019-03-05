---
title: Макросы класса окна
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::DECLARE_WND_CLASS
- atlwin/ATL::DECLARE_WND_SUPERCLASS
- atlwin/ATL::DECLARE_WND_CLASS_EX
ms.assetid: ce18681a-2bab-4453-9895-0f3ea47c2b24
ms.openlocfilehash: c4617a04c199741b97316122456e417a94275e89
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261002"
---
# <a name="window-class-macros"></a>Макросы класса окна

Эти макросы определяют служебных программ класса окна.

|||
|-|-|
|[DECLARE_WND_CLASS](#declare_wnd_class)|Позволяет указать имя класса окна.|
|[DECLARE_WND_CLASS2](#declare_wnd_class2)|(Visual Studio 2017 г.) Позволяет указать имя нового класса окна и включающего класса Оконная процедура которого будет использоваться новый класс.|
|[DECLARE_WND_SUPERCLASS](#declare_wnd_superclass)|Позволяет указать имя существующий класс окон, на котором будет основан новый класс окна.|
|[DECLARE_WND_CLASS_EX](#declare_wnd_class_ex)|Позволяет указать параметры типа класса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlwin.h

##  <a name="declare_wnd_class"></a>  DECLARE_WND_CLASS

Позволяет указать имя класса окна. Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления.

```
DECLARE_WND_CLASS( WndClassName )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
[in] Имя нового класса окна. Если значение равно NULL, ATL создаст имя класса окна.

### <a name="remarks"></a>Примечания

Если вы используете параметр /permissive-compiler, то DECLARE_WND_CLASS приведет к ошибке компилятора; Вместо этого используйте DECLARE_WND_CLASS2.

DECLARE_WND_CLASS позволяет указать имя нового класса окна, сведения о которой будут управляться [CWndClassInfo](cwndclassinfo-class.md). DECLARE_WND_CLASS определяет новый класс окна путем реализации статического следующую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

DECLARE_WND_CLASS задает следующие стили для нового окна:

- CS_HREDRAW

- CS_VREDRAW

- CS_DBLCLKS

DECLARE_WND_CLASS также задает цвет фона окна по умолчанию. Используйте [DECLARE_WND_CLASS_EX](#declare_wnd_class_ex) макрос для предоставления собственных стилей и цвет фона.

[CWindowImpl](cwindowimpl-class.md) использует макрос DECLARE_WND_CLASS создать окно, в зависимости от нового класса окна. Чтобы переопределить это поведение, используйте [DECLARE_WND_SUPERCLASS](#declare_wnd_superclass) макрос, или предоставить собственную реализацию [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) функции.

Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

##  <a name="declare_wnd_class2"></a>  DECLARE_WND_CLASS2

(Visual Studio 2017 г.) Подобен DECLARE_WND_CLASS, но с дополнительным параметром, чтобы избежать ошибки зависимое имя при компиляции с параметром /permissive-option.

```
DECLARE_WND_CLASS2( WndClassName, EnclosingClass )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
[in] Имя нового класса окна. Если значение равно NULL, ATL создаст имя класса окна.

*EnclosingClass*<br/>
[in] Имя класса окна, ограничивающий новый класс окна. Не может принимать значение NULL.

### <a name="remarks"></a>Примечания

Если вы используете /permissive-option, DECLARE_WND_CLASS приведет к ошибке компиляции, так как он содержит зависимое имя. DECLARE_WND_CLASS2 необходимо явно указывать имя класса, этот макрос используется и не вызывает ошибку в разделе /permissive-flag.
В противном случае этот макрос идентична [DECLARE_WND_CLASS](#declare_wnd_class).

##  <a name="declare_wnd_superclass"></a>  DECLARE_WND_SUPERCLASS

Позволяет указать параметры типа класса. Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления.

```
DECLARE_WND_SUPERCLASS( WndClassName, OrigWndClassName )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
[in] Имя окна класса суперкласса, будет *OrigWndClassName*. Если значение равно NULL, ATL создаст имя класса окна.

*OrigWndClassName*<br/>
[in] Имя существующего класса окна.

### <a name="remarks"></a>Примечания

Этот макрос можно указать имя класса окна, который будет суперкласса существующий класс окон. [CWndClassInfo](cwndclassinfo-class.md) управляет данными суперкласса.

DECLARE_WND_SUPERCLASS реализует следующие статические функции:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

По умолчанию [CWindowImpl](cwindowimpl-class.md) использует [DECLARE_WND_CLASS](#declare_wnd_class) макрос для создания окна на основании нового класса окна. Путем указания макроса DECLARE_WND_SUPERCLASS в `CWindowImpl`-производного класса, класс окна будет основываться на существующий класс, но будет использовать в процедуре окна. Этот прием называется создание надклассов.

Помимо использования DECLARE_WND_CLASS и DECLARE_WND_SUPERCLASS макросы, можно переопределить [GetWndClassInfo](cwindowimpl-class.md#getwndclassinfo) функцию со своей собственной реализации.

Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

##  <a name="declare_wnd_class_ex"></a>  DECLARE_WND_CLASS_EX

Позволяет указать имя существующий класс окон, на котором будет основан новый класс окна. Поместите этот макрос в элемент управления ActiveX библиотеки ATL класс элемента управления.

```
DECLARE_WND_CLASS_EX( WndClassName, style, bkgnd )
```

### <a name="parameters"></a>Параметры

*WndClassName*<br/>
[in] Имя нового класса окна. Если значение равно NULL, ATL создаст имя класса окна.

*Стиль*<br/>
[in] Стиль окна.

*фоновый*<br/>
[in] Цвет фона окна.

### <a name="remarks"></a>Примечания

Этот макрос можно указать параметры класса нового класса окна, сведения о которой будут управляться [CWndClassInfo](cwndclassinfo-class.md). DECLARE_WND_CLASS_EX определяет новый класс окна путем реализации статического следующую функцию:

[!code-cpp[NVC_ATL_Windowing#127](../../atl/codesnippet/cpp/window-class-macros_1.cpp)]

Если вы хотите использовать стили по умолчанию и цвет фона, используйте [DECLARE_WND_CLASS](#declare_wnd_class) макрос. Дополнительные сведения об использовании windows в ATL см. в статье [классы окон ATL](../../atl/atl-window-classes.md).

## <a name="see-also"></a>См. также

[Макросы](atl-macros.md)
