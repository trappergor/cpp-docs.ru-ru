---
title: Структура ABC | Документация Майкрософт
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
ms.openlocfilehash: 2c9aac181edb12df8904a2bc6d891d59c0067ecc
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339323"
---
# <a name="abc-structure"></a>Структура ABC
`ABC` Структура содержит ширину символов шрифта TrueType.  
  
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
 Определяет расстояние типа символа. Объект интервал — это расстояние для добавления к текущей позиции до начала рисования глифов символов.  
  
 *abcB*  
 Определяет расстояние B символа. Интервал B — ширина формируемого части глифов символов.  
  
 *abcC*  
 Определяет расстояние C символа. Интервал C — это расстояние добавляемый текущей позицией с целью предоставления пробел справа от символов глифа.  
  
## <a name="remarks"></a>Примечания  
 Общая ширина символа представляет сводку A, B и C пробелы. Объект или пространстве C может быть отрицательным для указания underhangs или выступать вниз.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)


