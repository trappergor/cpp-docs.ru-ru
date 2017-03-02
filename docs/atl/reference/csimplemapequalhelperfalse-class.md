---
title: "Класс CSimpleMapEqualHelperFalse | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSimpleMapEqualHelperFalse
- CSimpleMapEqualHelperFalse
- ATL.CSimpleMapEqualHelperFalse
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 68a08ffc0ba126c523a779e3d1a72217dead6235
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelperfalse-class"></a>Класс CSimpleMapEqualHelperFalse
Этот класс представляет вспомогательный класс для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Статический) Проверяет равенство двух ключей.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Статический) Возвращает значение false.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс признаков является дополнением к `CSimpleMap` класса. Он предоставляет метод для сравнения двух элементов, содержащихся в `CSimpleMap` объекта, в частности два значения элемента или два основных элементов.  
  
 Сравнение значений всегда будет возвращать значение false, а кроме того, будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. В ситуациях, где проверку равенства не определен достаточно, этот класс позволяет карты, содержащий пары ключ значение для правильной работы в большинстве методов, но не в форме четко определенные методы, зависящие от сравнения, таких как [CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="a-nameisequalkeya--csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey  
 Проверяет равенство двух ключей.  
  
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
  
##  <a name="a-nameisequalvaluea--csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 Возвращает значение false.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение false.  
  
### <a name="remarks"></a>Примечания  
 Этот метод всегда возвращает значение false и будет вызывать `ATLASSERT` с аргументом значение false, если когда-либо ссылки на него. Назначение `CSimpleMapEqualHelperFalse::IsEqualValue` — заставить методы с помощью сравнения сбой в форме четко определенные тесты на равенство не заданы правильно.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

