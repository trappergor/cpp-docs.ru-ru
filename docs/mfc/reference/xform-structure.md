---
title: Структура XFORM | Документация Майкрософт
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
ms.openlocfilehash: 6084882bed6690269fbb926f394159491d22978a
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885888"
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
 `XFORM` Структура указывает абсолютном преобразования "место на страницах". `eDx` И `eDy` члены задают компонентов горизонтальные и вертикальные преобразования, соответственно. В следующей таблице показаны, как используются другие элементы, в зависимости от операции:  
  
|Операция|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Косинус угла поворота|Синус угла поворота|Отрицательное синус угла поворота|Косинус угла поворота|  
|`Scaling`|Горизонтальное масштабирование компонентов|Nothing|Nothing|Вертикальный компонент масштабирования|  
|`Shear`|Nothing|Константа пропорциональность по горизонтали|Константа пропорциональность по вертикали|Nothing|  
|`Reflection`|Компонент горизонтальной отражения|Nothing|Nothing|Компонент вертикальной отражения|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)

