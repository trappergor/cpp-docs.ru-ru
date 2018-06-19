---
title: Структура ABC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61b5f67247b556b37cdf934f94c30947675533e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346494"
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


