---
title: "Структура XFORM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- XFORM
dev_langs:
- C++
helpviewer_keywords:
- XFORM structure
ms.assetid: 4fb4ef5b-05d2-4884-82d1-1cb8f7be6302
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2d23b3838f1e2dcabb2affb96fa6f18942581ff8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
 `XFORM` Структура указывает world места для преобразования места на странице. **EDx** и **eDy** члены указать компоненты горизонтального и вертикального перевода, соответственно. В следующей таблице показано, как использовать другие члены в зависимости от операции:  
  
|Операция|eM11|eM12|eM21|eM22|  
|---------------|----------|----------|----------|----------|  
|`Rotation`|Косинус угла поворота|Синус угла поворота|Отрицательные синус угла поворота|Косинус угла поворота|  
|**Масштабирование**|Горизонтальное масштабирование компонентов|Nothing|Nothing|Компонент вертикального масштабирования|  
|**Наклон**|Nothing|Константа пропорциональность по горизонтали|Константа пропорциональность по вертикали|Nothing|  
|**Отражение**|Компонент горизонтальной отражения|Nothing|Nothing|Компонент вертикальной отражения|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** wingdi.h  
  
## <a name="see-also"></a>См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)


