---
title: Структура CREATESTRUCT
ms.date: 11/04/2016
f1_keywords:
- CREATESTRUCT
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
ms.openlocfilehash: 1de42ba3e26f7a06918a69358083e68f142836cc
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694703"
---
# <a name="createstruct-structure"></a>Структура CREATESTRUCT

`CREATESTRUCT` Структура определяет параметры инициализации, передаваемые в процедуру окна приложения.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagCREATESTRUCT {
    LPVOID lpCreateParams;
    HANDLE hInstance;
    HMENU hMenu;
    HWND hwndParent;
    int cy;
    int cx;
    int y;
    int x;
    LONG style;
    LPCSTR lpszName;
    LPCSTR lpszClass;
    DWORD dwExStyle;
} CREATESTRUCT;
```

#### <a name="parameters"></a>Параметры

*lpCreateParams*<br/>
Указывает данные, используемые для создания окна.

*hInstance*<br/>
Определяет дескриптор модуля, которому принадлежит окно, новый экземпляр модуля.

*hMenu*<br/>
Идентифицирует меню для использования нового окна. Если дочернее окно, содержащее целочисленный идентификатор.

*hwndParent*<br/>
Определяет окно, которому принадлежит новое окно. Этот элемент имеет значение NULL, если новое окно является окном верхнего уровня.

*CY*<br/>
Высота нового окна.

*CX*<br/>
Ширина нового окна.

*y*<br/>
Указывает y координата левого верхнего нового окна. Координаты указываются относительно родительского окна, если новое окно — дочернее окно; в противном случае координаты определяются относительно экрана.

*x*<br/>
Указывает Координата по оси x верхнего левого угла нового окна. Координаты указываются относительно родительского окна, если новое окно — дочернее окно; в противном случае координаты определяются относительно экрана.

*Стиль*<br/>
Указывает новое окно [стиля](../../mfc/reference/styles-used-by-mfc.md).

*lpszName*<br/>
Указатель на заканчивающуюся нулем строку, указывающее имя нового окна.

*lpszClass*<br/>
Указывает на заканчивающуюся нулем строку, указывающее имя класса новое окно Windows ( [WNDCLASS](/windows/desktop/api/winuser/ns-winuser-tagwndclassa) структуры; Дополнительные сведения см. в Windows SDK).

*dwExStyle*<br/>
Указывает [расширенный стиль](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) для нового окна.

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)

