---
title: Класс CSimpleMapEqualHelper | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d629806582d7ad9902ef5ca0d9425d6f1ecd7d7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879699"
---
# <a name="csimplemapequalhelper-class"></a>Класс CSimpleMapEqualHelper
Этот класс представляет вспомогательный объект для [CSimpleMap](../../atl/reference/csimplemap-class.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>Параметры  
 *TKey*  
 Ключевым элементом.  
  
 *TVal*  
 Значение элемента.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Статический) Проверяет два ключа на равенство.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Статический) Сравнивает два значения на равенство.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс признаков является дополнением к `CSimpleMap` класса. Он предоставляет методы для сравнения двух `CSimpleMap` объекта элементов (в частности, ключ и значение компоненты) на предмет равенства. По умолчанию ключи и значения сравниваются с помощью **operator==()**, но если сопоставление содержит сложные типы данных, которые не хватает собственные оператор равенства, этот класс можно переопределить, указав дополнительные необходимые функциональные возможности.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey  
 Проверяет два ключа на равенство.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Параметры  
 *K1*  
 Первый ключ.  
  
 *K2*  
 Второй ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ключи равны; значение false в противном случае.  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue  
 Сравнивает два значения на равенство.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>Параметры  
 *версии 1*  
 Первое значение в вычитании.  
  
 *v2*  
 Второе значение в вычитании.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если значения равны, значение false в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
