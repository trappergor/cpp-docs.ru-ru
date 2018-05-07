---
title: Структура XFORM | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure [MFC]
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a1c3a8abd39f7f190f36a18e7691475d951cab8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|**масштабирование**|Горизонтального масштабирования компонента|Nothing|Nothing|Вертикального масштабирования компонента|  
|**Наклон**|Nothing|Константа горизонтальной пропорциональность|Вертикальная пропорциональность-константа|Nothing|  
|**Отражение**|Компонент горизонтальной отражения|Nothing|Nothing|Компонент вертикальной отражения|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

