---
title: Структура LOGBRUSH | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure [MFC]
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b868efed07f786a78c516862e1f88d2310a7c05d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208782"
---
# <a name="logbrush-structure"></a>Структура LOGBRUSH
`LOGBRUSH` Структура определяет стиль, цвет и шаблон физических кисти. Он используется Windows [CreateBrushIndirect](/windows/desktop/api/wingdi/nf-wingdi-createbrushindirect) и [ExtCreatePen](/windows/desktop/api/wingdi/nf-wingdi-extcreatepen) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>Параметры  
 *lbStyle*  
 Задает стиль кисти. `lbStyle` Член должен быть одним из следующих стилей:  
  
- Кисть шаблон BS_DIBPATTERN объект определяется аппаратно независимый точечный рисунок (DIB) спецификации. Если *lbStyle* является BS_DIBPATTERN, `lbHatch` член содержит дескриптор упакованного DIB.  
  
- Кисть шаблон BS_DIBPATTERNPT объект определяется аппаратно независимый точечный рисунок (DIB) спецификации. Если *lbStyle* является BS_DIBPATTERNPT, `lbHatch` член содержит указатель на упакованный DIB.  
  
- BS_HATCHED Hatched кисть.  
  
- BS_HOLLOW пустой кисти.  
  
- BS_NULL совпадение с кодом BS_HOLLOW.  
  
- Шаблон BS_PATTERN кисти, определенный Битовая карта памяти.  
  
- BS_SOLID сплошную кисть.  
  
 *lbColor*  
 Задает цвет, в которой кисть, которая будет отображаться. Если *lbStyle* стиль BS_HOLLOW или BS_PATTERN *lbColor* учитывается. Если *lbStyle* BS_DIBPATTERN или BS_DIBPATTERNBT младшее слово из *lbColor* указывает ли `bmiColors` членами [BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md) структуры в настоящее время реализованных логическую палитру содержать явные красный, зеленый, синий значений (RGB) или индексы. `lbColor` Член должен быть одним из следующих значений:  
  
- DIB_PAL_COLORS таблица цветов содержит массив 16-разрядными индексами, в настоящее время реализованных логическую палитру.  
  
- DIB_RGB_COLORS таблица цветов содержит литеральные значения RGB.  
  
 *lbHatch*  
 Задает стиль штриховки. Значение зависит от стиля кисти, определяется *lbStyle*. Если *lbStyle* является BS_DIBPATTERN, `lbHatch` член содержит дескриптор упакованного DIB. Если *lbStyle* является BS_DIBPATTERNPT, `lbHatch` член содержит указатель на упакованный DIB. Если *lbStyle* является BS_HATCHED, `lbHatch` член задает ориентацию линии, используемые для создания штриховки. Он может принимать одно из следующих значений:  
  
- HS_BDIAGONAL объект 45 градусов вверх, слева направо штриховки  
  
- HS_CROSS горизонтальной и вертикальной клетчатый  
  
- Клетчатый HS_DIAGCROSS 45 градусов  
  
- HS_FDIAGONAL объект 45 градусов вниз, слева направо штриховки  
  
- HS_HORIZONTAL Горизонтальная штриховка  
  
- Штриховка по вертикали HS_VERTICAL  
  
 Если *lbStyle* является BS_PATTERN, *lbHatch* — это дескриптор для точечного рисунка, который определяет шаблон. Если *lbStyle* BS_SOLID или BS_HOLLOW, *lbHatch* учитывается.  
  
## <a name="remarks"></a>Примечания  
 Несмотря на то что *lbColor* определяет цвет переднего плана штриховой кистью, [CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode) и [CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor) функции управления цветом фона.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

