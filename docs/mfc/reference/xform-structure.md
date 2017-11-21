---
title: "Структура XFORM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XFORM
dev_langs: C++
helpviewer_keywords: XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3c9e5978d82b1bbaed08eaa05dda53c78160579f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="xform-structure"></a>Структура XFORM
`XFORM` Структура имеет следующий вид:  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct  tagXFORM {  /* xfrm */  
    FLOAT eM11;  
    FLOAT eM12;  
    FLOAT eM21;  
    FLOAT eM22;  
    FLOAT eDx;  
    FLOAT eDy;  
} XFORM;  
```  
  
## <a name="remarks"></a>Примечания  
 `XFORM` Структура указывает абсолютном пространстве для преобразования места на странице. **EDx** и **eDy** члены указывать компонентов горизонтальные и вертикальные преобразования, соответственно. В следующей таблице показано, как использовать другие члены в зависимости от операции:  
  
|Операция|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Косинус угла поворота|Синус угла поворота|Отрицательное синус угла поворота|Косинус угла поворота|  
|**Масштабирование**|Горизонтального масштабирования компонента|Nothing|Nothing|Вертикального масштабирования компонента|  
|**Наклон**|Nothing|Константа горизонтальной пропорциональность|Вертикальная пропорциональность-константа|Nothing|  
|**Отражение**|Компонент горизонтальной отражения|Nothing|Nothing|Компонент вертикальной отражения|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

