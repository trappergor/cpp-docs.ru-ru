---
title: "Структура LOGBRUSH | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: eea7caf6139fd43dd77163271701d170c7a744e2
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="logbrush-structure"></a>Структура LOGBRUSH
`LOGBRUSH` Структура определяет стиль, цвет и шаблон физических кисти. Он используется системой Windows [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487) и [ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Параметры  
 `lbStyle`  
 Задает стиль кисти. `lbStyle` Элемент должен быть один из следующих стилей:  
  
- **BS_DIBPATTERN** шаблон кисти, определенных спецификацией аппаратно независимым точечным рисунком (DIB). Если `lbStyle` — **BS_DIBPATTERN**, **lbHatch** член содержит дескриптор упакованным DIB.  
  
- **BS_DIBPATTERNPT** шаблон кисти, определенных спецификацией аппаратно независимым точечным рисунком (DIB). Если `lbStyle` — **BS_DIBPATTERNPT**, **lbHatch** члена содержит указатель на упакованный DIB.  
  
- **BS_HATCHED** Hatched кисти.  
  
- **BS_HOLLOW** пустая кисти.  
  
- **BS_NULL** как **BS_HOLLOW**.  
  
- **BS_PATTERN** шаблона кисти определяется памяти растрового изображения.  
  
- **BS_SOLID** сплошной кисти.  
  
 `lbColor`  
 Задает цвет, в котором будет рисоваться кисти. Если `lbStyle` — **BS_HOLLOW** или **BS_PATTERN** стиля, **lbColor** игнорируется. Если `lbStyle` — **BS_DIBPATTERN** или **BS_DIBPATTERNBT**, младшее слово из **lbColor** указывает ли **bmiColors** члены [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) структура содержит явную красный, зеленый, синий (RGB) значения или индексов в палитре в настоящее время реализованных логических. **LbColor** член должен быть одним из следующих значений:  
  
- **DIB_PAL_COLORS** таблица цветов состоит из массива 16-разрядными индексами в палитре в настоящее время реализованных логических.  
  
- **DIB_RGB_COLORS** таблица цветов содержит литеральные значения RGB.  
  
 *lbHatch*  
 Задает стиль штриховки. Значение зависит от стиля кисти, описанного в `lbStyle`. Если `lbStyle` — **BS_DIBPATTERN**, **lbHatch** член содержит дескриптор упакованным DIB. Если `lbStyle` — **BS_DIBPATTERNPT**, **lbHatch** члена содержит указатель на упакованный DIB. Если `lbStyle` — **BS_HATCHED**, **lbHatch** член задает ориентацию линии, используемые для создания штриховки. Он может принимать одно из следующих значений:  
  
- `HS_BDIAGONAL`45 градусов штриховку вверх, слева направо  
  
- `HS_CROSS`Горизонтальные и вертикальные штриховки  
  
- `HS_DIAGCROSS`штриховки 45 градусов  
  
- `HS_FDIAGONAL`45 градусов штриховку вниз, слева направо  
  
- `HS_HORIZONTAL`Горизонтальная штриховка  
  
- `HS_VERTICAL`Вертикальная штриховка  
  
 Если `lbStyle` — **BS_PATTERN**, **lbHatch** является дескриптором растровому изображению, которое определяет шаблон. Если `lbStyle` — **BS_SOLID** или **BS_HOLLOW**, **lbHatch** игнорируется.  
  
## <a name="remarks"></a>Примечания  
 Хотя **lbColor** определяет цвет штриховой кистью, [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) и [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) функции управления цветом фона.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


