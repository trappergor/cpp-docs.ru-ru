---
title: "Структура ABCFLOAT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ABCFLOAT
dev_langs: C++
helpviewer_keywords: ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 983439d773a7ded59e09c1385bce4febc9979ef6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="abcfloat-structure"></a>Структура ABCFLOAT
`ABCFLOAT` Структура содержит A, B и C ширина символа шрифта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _ABCFLOAT { /* abcf */  
    FLOAT abcfA;  
    FLOAT abcfB;  
    FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### <a name="parameters"></a>Параметры  
 *abcfA*  
 Задает расстояние типа символа. Объект интервал — это расстояние для добавления в текущее положение перед рисованием символ глиф.  
  
 *abcfB*  
 Задает расстояние B символа. Интервал B-ширина отображаемой части символ глиф.  
  
 *abcfC*  
 Задает расстояние C символа. C интервал — это расстояние добавляемый текущей позицией с целью обеспечения пустого пространства справа от символа глифа.  
  
## <a name="remarks"></a>Примечания  
 Ширина A, B и C измеряются вдоль базовой линией шрифта. Шаг символ (общая ширина) символ — это сумма пространств A, B и C. A и C пространства может быть отрицательным для указания underhangs или выступать вниз.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

