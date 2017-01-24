---
title: "Структура LOGPEN | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LOGPEN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LOGPEN - структура"
ms.assetid: a89e8690-6b61-4af5-990c-7c82da24f3b0
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура LOGPEN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

 `LOGPEN` Структура определяет стиль, ширину и цвет пера, графический объект, используемый для рисования линий и границ.  [CPen::CreatePenIndirect](../Topic/CPen%20Class.md#cpen__createpenindirect) функция использует `LOGPEN` структуры.  
  
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
  
- **PS_DASH** создает штрихового пера. (Действует только в том случае, если ширина пера равна 1.)  
  
- **PS_DOT** создает точечный перо. (Действует только в том случае, если ширина пера равна 1.)  
  
- **PS_DASHDOT** создает перо с чередованием, дефисы и точки. (Действует только в том случае, если ширина пера равна 1.)  
  
- **PS_DASHDOTDOT** создает с сменяющих друг друга штрихов и double точек пера. (Действует только в том случае, если ширина пера равна 1.)  
  
- **PS_NULL** создает null перо.  
  
- **PS_INSIDEFRAME** создает перо, рисующее строки внутри кадра замкнутые фигуры, созданные выходные данные функций GDI, определяющие ограничивающий прямоугольник (например, **эллипс**, **прямоугольник**, `RoundRect`, `Pie`, и `Chord` функции-члены). При использовании этого стиля с помощью GDI выходных данных функции, которые не указывают ограничивающий прямоугольник (например, `LineTo` функции-члена), область рисования пера не ограничивается кадра.  
  
     Если перо имеет **PS_INSIDEFRAME** стиль и цвет, который не соответствует цвет в таблице логических цветов нарисован с помощью сглаженный цвет пера.  **PS_SOLID** стиль пера не может использоваться для создания с сглаженный цвет пера.  **PS_INSIDEFRAME** стиль идентична **PS_SOLID** Если ширину пера меньше или равно 1.  
  
     При **PS_INSIDEFRAME** с GDI-объекты, созданные функциями, кроме используется стиль **эллипс**, **прямоугольник**, и `RoundRect`, строка не может быть полностью внутри заданного фрейма.  
  
 *lopnWidth*  
 Задает ширину пера в логических единицах. Если **lopnWidth** член равен 0, перо одну точку на устройствах растровых независимо от текущего режима сопоставления.  
  
 *lopnColor*  
 Задает цвет пера.  
  
## <a name="remarks"></a>Заметки  
  **y** значение в [ТОЧКИ](../../mfc/reference/point-structure1.md) Структура для **lopnWidth** элемент не используется.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPen::CreatePenIndirect](../Topic/CPen%20Class.md#cpen__createpenindirect)

