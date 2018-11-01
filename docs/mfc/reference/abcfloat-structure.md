---
title: Структура ABCFLOAT
ms.date: 11/04/2016
f1_keywords:
- ABCFLOAT
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
ms.openlocfilehash: b9e3923e8c70e38fe5efe959db8da43118cc6445
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443668"
---
# <a name="abcfloat-structure"></a>Структура ABCFLOAT

`ABCFLOAT` Структура содержит A, B и C ширину символов шрифта.

## <a name="syntax"></a>Синтаксис

```
typedef struct _ABCFLOAT { /* abcf */
    FLOAT abcfA;
    FLOAT abcfB;
    FLOAT abcfC;
} ABCFLOAT;
```

#### <a name="parameters"></a>Параметры

*abcfA*<br/>
Определяет расстояние типа символа. Объект интервал — это расстояние для добавления к текущей позиции до начала рисования глифов символов.

*abcfB*<br/>
Определяет расстояние B символа. Интервал B — ширина формируемого части глифов символов.

*abcfC*<br/>
Определяет расстояние C символа. Интервал C — это расстояние добавляемый текущей позицией с целью предоставления пробел справа от символов глифа.

## <a name="remarks"></a>Примечания

Значения ширины A, B и C измеряются по базовой линии шрифта. Символ приращение (общая ширина) знака равно сумме A, B и C пробелы. Объект или пространстве C может быть отрицательным для указания underhangs или выступать вниз.

## <a name="requirements"></a>Требования

**Заголовок:** wingdi.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

