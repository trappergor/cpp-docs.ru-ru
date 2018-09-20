---
title: Структура CREATESTRUCT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 880cbbde261caf804e16e9eb759abb213cb84f60
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422432"
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
Указывает на заканчивающуюся нулем строку, указывающее имя класса новое окно Windows ( [WNDCLASS](https://msdn.microsoft.com/library/windows/desktop/ms633576) структуры; Дополнительные сведения см. в Windows SDK).

*dwExStyle*<br/>
Указывает [расширенный стиль](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles) для нового окна.

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


