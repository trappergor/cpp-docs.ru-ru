---
title: "Класс CDefaultCompareTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDefaultCompareTraits<T>
- ATL::CDefaultCompareTraits
- ATL.CDefaultCompareTraits
- ATL::CDefaultCompareTraits<T>
- CDefaultCompareTraits
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
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
ms.openlocfilehash: 1d1253b7a7d69024465627cc9fb37fcd2afba693
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultcomparetraits-class"></a>Класс CDefaultCompareTraits
Этот класс предоставляет функции сравнения элемент по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранящихся в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Статический) Эта функция используется для сравнения на равенство двух элементов.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Статический) Эта функция вызывается для определения элемента больше и меньше.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс содержит два статических функций для сравнения элементов, хранящихся в объекте класса коллекции. Этот класс используется [CDefaultElementTraits класса](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-namecompareelementsa--cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 Эта функция используется для сравнения на равенство двух элементов.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Параметры  
 `element1`  
 Первый элемент  
  
 `element2`  
 Второй элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию эта функция реализуется равенства ( `==`) оператор. Для объектов, отличных от простых типов данных эта функция может потребоваться переопределить.  
  
##  <a name="a-namecompareelementsordereda--cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 Эта функция вызывается для определения элемента больше и меньше.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Параметры  
 `element1`  
 Первый элемент  
  
 `element2`  
 Второй элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение типа integer, зависимости в следующей таблице:  
  
|Условие|Возвращаемое значение|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Примечания  
 Реализация по умолчанию эта функция использует `==`, ** \< **, и ** > ** операторы. Для объектов, отличных от простых типов данных эта функция может потребоваться переопределить.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

