---
title: "Структура ABC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ABC
dev_langs:
- C++
helpviewer_keywords:
- ABC structure
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: c8b49cd8a94c5ff580393814be08b1819a1eca52
ms.lasthandoff: 02/24/2017

---
# <a name="abc-structure"></a>Структура ABC
**ABC** структура содержит ширину символов шрифта TrueType.  
  
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
 Задает расстояние типа символа. Значение интервал — это расстояние для добавления в текущее положение перед рисованием символ глиф.  
  
 *abcB*  
 Задает расстояние B символа. Интервал B — ширина формируемого части глифов символов.  
  
 *abcC*  
 Задает расстояние C символа. C интервал — это расстояние Добавление текущей позицией с целью обеспечения пустого пространства справа от символа глиф.  
  
## <a name="remarks"></a>Примечания  
 Общая ширина знака получается суммированием A, B и C пробелов. Объект или места C может быть отрицательным для указания underhangs или выступать вниз.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)



