---
title: Структура ABC
ms.date: 11/04/2016
f1_keywords:
- ABC
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
ms.openlocfilehash: f899a84ddbe5ca3ec3abd4dff135a585aa61eaa9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549569"
---
# <a name="abc-structure"></a>Структура ABC

`ABC` Структура содержит ширину символов шрифта TrueType.

## <a name="syntax"></a>Синтаксис

```
typedef struct _ABC { /* abc */
    int abcA;
    UINT abcB;
    int abcC;
} ABC;
```

#### <a name="parameters"></a>Параметры

*abcA*<br/>
Определяет расстояние типа символа. Объект интервал — это расстояние для добавления к текущей позиции до начала рисования глифов символов.

*abcB*<br/>
Определяет расстояние B символа. Интервал B — ширина формируемого части глифов символов.

*abcC*<br/>
Определяет расстояние C символа. Интервал C — это расстояние добавляемый текущей позицией с целью предоставления пробел справа от символов глифа.

## <a name="remarks"></a>Примечания

Общая ширина символа представляет сводку A, B и C пробелы. Объект или пространстве C может быть отрицательным для указания underhangs или выступать вниз.

## <a name="requirements"></a>Требования

**Заголовок:** wingdi.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

