---
title: "Структура ABC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ABC
dev_langs: C++
helpviewer_keywords: ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ba8add08fcd5ff3d7343477aafa7d910885b0b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="abc-structure"></a>Структура ABC
**ABC** структура содержит ширина символа шрифтом TrueType.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _ABC { /* abc */  
    int abcA;  
    UINT abcB;  
    int abcC;  
} ABC;  
```  
  
#### <a name="parameters"></a>Параметры  
 *abcA*  
 Задает расстояние типа символа. Объект интервал — это расстояние для добавления в текущее положение перед рисованием символ глиф.  
  
 *abcB*  
 Задает расстояние B символа. Интервал B-ширина отображаемой части символ глиф.  
  
 *abcC*  
 Задает расстояние C символа. C интервал — это расстояние добавляемый текущей позицией с целью обеспечения пустого пространства справа от символа глифа.  
  
## <a name="remarks"></a>Примечания  
 Общая ширина символа является суммирование A, B и C пробелы. A и C пространства может быть отрицательным для указания underhangs или выступать вниз.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


