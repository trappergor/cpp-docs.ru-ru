---
title: Структура LOGPEN | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGPEN
dev_langs:
- C++
helpviewer_keywords:
- LOGPEN structure [MFC]
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0fa2a4b422a7bd1f36fc46837adec4136b693fb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064958"
---
# <a name="logpen-structure"></a>Структура LOGPEN

`LOGPEN` Структура определяет стиль, ширину и цвет пера, графический объект, используемый для рисования линий и границ. [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) функция использует `LOGPEN` структуры.

## <a name="syntax"></a>Синтаксис

```
typedef struct tagLOGPEN {  /* lgpn */
    UINT lopnStyle;
    POINT lopnWidth;
    COLORREF lopnColor;
} LOGPEN;
```

#### <a name="parameters"></a>Параметры

*lopnStyle*<br/>
Указывает тип пера. Этот член может принимать одно из следующих значений:

- PS_SOLID создает сплошной перо.

- PS_DASH создает штрихового пера. (Доступно только в том случае, если перо ширина равна 1.)

- PS_DOT создает точечно перо. (Доступно только в том случае, если перо ширина равна 1.)

- Создает PS_DASHDOT пера с чередованием дефисы и точки. (Доступно только в том случае, если перо ширина равна 1.)

- PS_DASHDOTDOT создает a перо сменяющих друг друга штрихов и double точек. (Доступно только в том случае, если перо ширина равна 1.)

- PS_NULL создает null перо.

- PS_INSIDEFRAME создает созданных перо, рисующее строку в фрейме замкнутые фигуры в GDI выходные данные функции, определяющие ограничивающий прямоугольник (например, `Ellipse`, `Rectangle`, `RoundRect`, `Pie`, и `Chord` член функции). Если этот стиль используется с GDI выходные данные функции, которые задают ограничивающий прямоугольник (например, `LineTo` функция-член), области рисования пера не ограничивается кадр.

   Если перо PS_INSIDEFRAME стиль и цвет, который не соответствует цвета в таблице логических цветов, пера рисуется пером сглаженный цвет. Стиль пера PS_SOLID не может использоваться для создания с сглаженный цвет пера. Стиль PS_INSIDEFRAME идентична PS_SOLID, если ширина пера меньше или равно 1.

   При использовании стиля PS_INSIDEFRAME со объекты GDI созданные функциями, отличное от `Ellipse`, `Rectangle`, и `RoundRect`, строки не могут быть полностью внутри заданного фрейма.

*lopnWidth*<br/>
Задает ширину пера, в логических единицах. Если `lopnWidth` члена равно 0, перо находится одну точку на устройствах растровых независимо от текущего режима сопоставления.

*lopnColor*<br/>
Задает цвет пера.

## <a name="remarks"></a>Примечания

`y` Значение в [ТОЧКИ](../../mfc/reference/point-structure1.md) структуры для `lopnWidth` элемент не используется.

## <a name="requirements"></a>Требования

**Заголовок:** wingdi.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

