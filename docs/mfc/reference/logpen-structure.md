---
title: Структура LOGPEN | Документы Microsoft
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
ms.openlocfilehash: 4c0e07ce3a38eaca54e860ebe821924c0f564c69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="logpen-structure"></a>Структура LOGPEN
`LOGPEN` Структура определяет стиль, ширину и цвет фона для пера, графический объект, используемый для рисования линий и границ. [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect) функция использует `LOGPEN` структуры.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct tagLOGPEN {  /* lgpn */  
    UINT lopnStyle;  
    POINT lopnWidth;  
    COLORREF lopnColor;  
} LOGPEN;  
```  
  
#### <a name="parameters"></a>Параметры  
 *lopnStyle*  
 Указывает тип пера. Этот член может принимать одно из следующих значений:  
  
- **PS_SOLID** создает сплошной перо.  
  
- **PS_DASH** создает пунктирного пера. (Действительно только в том случае, когда толщина пера равна 1.)  
  
- **PS_DOT** создает пунктирная перо. (Действительно только в том случае, когда толщина пера равна 1.)  
  
- **PS_DASHDOT** создает перо с чередованием, дефисы и точки. (Действительно только в том случае, когда толщина пера равна 1.)  
  
- **PS_DASHDOTDOT** создает перо с чередованием, дефисы и точки double. (Действительно только в том случае, когда толщина пера равна 1.)  
  
- **PS_NULL** создает null перо.  
  
- **PS_INSIDEFRAME** создает перо, рисуется линия внутри фрейма, созданные выходные функции GDI, определяющие ограничивающий прямоугольник замкнутых фигур (например, **эллипса**, **прямоугольник**, `RoundRect`, `Pie`, и `Chord` функций-членов). При использовании этого стиля с использованием GDI выходные данные функции, которые задают ограничивающий прямоугольник (например, `LineTo` функции-члена), область рисования пера не ограничивается кадра.  
  
     Если есть пера **PS_INSIDEFRAME** стиль и цвет, который не соответствует цвета в таблице логических цветов нарисован с помощью сглаженный цвет пера. **PS_SOLID** стиль пера не может использоваться для создания с сглаженный цвет пера. **PS_INSIDEFRAME** стиль идентична **PS_SOLID** Если толщина пера меньше или равно 1.  
  
     Когда **PS_INSIDEFRAME** используется стиль с GDI-объекты, созданные функциями, отличный от **эллипса**, **прямоугольник**, и `RoundRect`, строки не могут быть полностью внутри заданного фрейма.  
  
 *lopnWidth*  
 Задает ширину пера в логических единицах. Если **lopnWidth** члена равно 0, перо имеет одну точку на устройствах растровых независимо от того, какой режим сопоставления.  
  
 *lopnColor*  
 Задает цвет пера.  
  
## <a name="remarks"></a>Примечания  
 **y** значение в [ТОЧКИ](../../mfc/reference/point-structure1.md) структура для **lopnWidth** элемент не используется.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../../mfc/reference/cpen-class.md#createpenindirect)

