---
title: Класс CSimpleMapEqualHelperFalse | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bebd9c6628924b5927fb48518925bdd665b0ee14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360022"
---
# <a name="csimplemapequalhelperfalse-class"></a>Класс CSimpleMapEqualHelperFalse
Этот класс представляет вспомогательный класс для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Статический) Проверяет два ключа на равенство.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Статический) Возвращает значение false.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс признаки является дополнением к `CSimpleMap` класса. Он предоставляет метод для сравнения двух элементов, содержащихся в `CSimpleMap` объекта, в частности два значения элемента или два основных элементов.  
  
 Сравнение значений всегда будет возвращать значение false, а кроме того, будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. В ситуациях, когда проверку равенства не определено недостаточно, этот класс позволяет карты, содержащий пары ключ значение для правильной работы для большинства методов, но в форме четко определенных для методов, зависящих от сравнения, такие как сбой [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey  
 Проверяет два ключа на равенство.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Параметры  
 `k1`  
 Первый ключ.  
  
 `k2`  
 Второй ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ключи равны false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает метод [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue  
 Возвращает значение false.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод всегда возвращает значение false и будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. Назначение `CSimpleMapEqualHelperFalse::IsEqualValue` можно принудительно методов с помощью сравнения возвращать ошибку четко определенным образом, если не были правильно определены проверок на равенство.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
