---
title: Структура RGNDATA | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d40cd86cff4c3e58e88f9d17a551dc789bd1db4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398219"
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

