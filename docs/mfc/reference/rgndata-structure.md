---
title: Структура RGNDATA
ms.date: 11/04/2016
f1_keywords:
- RGNDATA
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
ms.openlocfilehash: d6ee25b490aa5c7055b4e8ccf63939fbdd8dd4ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638143"
---
# <a name="rgndata-structure"></a>Структура RGNDATA

`RGNDATA` Структура содержит заголовок и массив прямоугольников, которые составляют регион. Эти прямоугольники, отсортированный сверху вниз слева направо, не перекрываются.

## <a name="syntax"></a>Синтаксис

```
typedef struct _RGNDATA { /* rgnd */
    RGNDATAHEADER rdh;
    char Buffer[1];
} RGNDATA;
```

#### <a name="parameters"></a>Параметры

*rdh*<br/>
Указывает [RGNDATAHEADER](/windows/desktop/api/wingdi/ns-wingdi-_rgndataheader) структуры. (Дополнительные сведения об этой структуре см. в разделе Windows SDK.) Члены этой структуры укажите тип области (если он является прямоугольной или форме трапеции), количеством прямоугольников, составляющие области, размер буфера, который содержит прямоугольник структуры, и так далее.

*буфер*<br/>
Указывает буфер произвольного размера, который содержит [RECT](../../mfc/reference/rect-structure1.md) структур, составляющих области.

## <a name="requirements"></a>Требования

**Заголовок:** wingdi.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)<br/>
[CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

