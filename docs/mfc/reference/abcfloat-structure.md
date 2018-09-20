---
title: Структура ABCFLOAT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABCFLOAT
dev_langs:
- C++
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a9bbece0773c14a4a8b545bc56209bf682e22c0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375418"
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

