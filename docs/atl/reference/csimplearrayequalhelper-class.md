---
title: Класс CSimpleArrayEqualHelper | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6660f72dbd91a41670b3c5f8772d21caf4b8abc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362132"
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
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Статический) Проверка двух `CSimpleArray` объекта элементов на предмет равенства.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс признаки является дополнением к `CSimpleArray` класса. Он предоставляет метод для сравнения двух элементов, хранящихся в `CSimpleArray` объекта. По умолчанию элементы сравниваются с помощью **operator=()**, но если в массиве содержатся сложные типы данных которых не хватает собственные оператор равенства, необходимо переопределить этот класс.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual  
 Проверка двух `CSimpleArray` объекта элементов на предмет равенства.  
  
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
