---
title: "Класс CSimpleArrayEqualHelper | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4a87879683257c66de5fe4e720dd29fa4c47031d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelper-class"></a>Класс CSimpleArrayEqualHelper
Этот класс представляет вспомогательный класс для [CSimpleArray](../../atl/reference/csimplearray-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Производный класс.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Статический) Сравнивает два `CSimpleArray` объекта элементов на предмет равенства.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс признаков является дополнением к `CSimpleArray` класса. Он предоставляет метод для сравнения двух элементов, сохраненные в `CSimpleArray` объекта. По умолчанию элементы сравниваются с помощью **operator=()**, но если массив содержит сложные типы данных, не имеющих свои собственные оператор равенства, необходимо переопределить этот класс.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
 Сравнивает два `CSimpleArray` объекта элементов на предмет равенства.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>Параметры  
 *T1*  
 Объект типа T.  
  
 *T2*  
 Объект типа T.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны false в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleArray](../../atl/reference/csimplearray-class.md)   
 [Класс CSimpleArrayEqualHelperFalse](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

