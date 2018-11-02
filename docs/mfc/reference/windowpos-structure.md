---
title: Структура WINDOWPOS
ms.date: 11/04/2016
f1_keywords:
- WINDOWPOS
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
ms.openlocfilehash: 16d9122a4141d2516118304fcdb4dd1b8fc14421
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439433"
---
# <a name="windowpos-structure"></a>Структура WINDOWPOS

`WINDOWPOS` Структура содержит сведения о размере и положение окна.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagWINDOWPOS { /* wp */
    HWND hwnd;
    HWND hwndInsertAfter;
    int x;
    int y;
    int cx;
    int cy;
    UINT flags;
} WINDOWPOS;
```

#### <a name="parameters"></a>Параметры

*HWND*<br/>
Определяет окно.

*hwndInsertAfter*<br/>
Определяет окно, за которым помещается в этом окне.

*x*<br/>
Задает положение левого края окна.

*y*<br/>
Задает положение правой границы окна.

*CX*<br/>
Ширина окна в пикселях.

*CY*<br/>
Высота окна в пикселях.

*flags*<br/>
Указывает параметры размещения окна. Этот член может принимать одно из следующих значений:

- SWP_DRAWFRAME рисует кадр (определенной в описании класса окна) вокруг окна. Окно получает сообщение WM_NCCALCSIZE.

- Отправляет SWP_FRAMECHANGED WM_NCCALCSIZE сообщения в окно, даже если размер окна не изменяется. Если этот флаг не задан, WM_NCCALCSIZE отправляется только в том случае, при изменении размера окна.

- SWP_HIDEWINDOW скрывает окно.

- SWP_NOACTIVATE не активирует окно.

- SWP_NOCOPYBITS удаляет все содержимое клиентской области. Если этот флаг не задан, сохраняются и скопировать обратно в клиентской области после размера или положения окна допустимое содержимое клиентской области.

- Сохраняет SWP_NOMOVE текущей позиции (игнорирует `x` и `y` членов).

- SWP_NOOWNERZORDER не меняет позицию для окна-владельца в Z-порядке.

- SWP_NOSIZE сохраняет текущий размер (игнорирует `cx` и `cy` членов).

- SWP_NOREDRAW не будут перерисовываться изменения.

- SWP_NOREPOSITION совпадение с кодом SWP_NOOWNERZORDER.

- SWP_NOSENDCHANGING предотвращает получение WM_WINDOWPOSCHANGING сообщения окна.

- Текущую систему заказа на сохраняет SWP_NOZORDER (игнорирует `hwndInsertAfter` член).

- SWP_SHOWWINDOW Отображение окна.

## <a name="requirements"></a>Требования

**Заголовок:** winuser.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

