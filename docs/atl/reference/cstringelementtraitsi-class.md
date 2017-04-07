---
title: "Класс CStringElementTraitsI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
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
ms.openlocfilehash: 995c4798f92db3b3f065bf2176ab52ff53d282b0
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraitsi-class"></a>Класс CStringElementTraitsI
Этот класс предоставляет статические функции, связанные с строк, хранящихся в коллекции объектов класса. Это похоже на [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), но выполняет сравнение без учета регистра.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>  
class CStringElementTraitsI : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранящихся в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объекте класса коллекции.|  
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Тип данных, использовать для получения элементов из объекта класса коллекции.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](#compareelements)|Эта функция статических для сравнения двух строковых элементов на равенство, без учета различия регистра.|  
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Эта функция статических для сравнения двух строковых элементов, без учета различия регистра.|  
|[CStringElementTraitsI::Hash](#hash)|Эта функция статических для вычисления хэш-значение для заданной строки элемента.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции для сравнения строк, а также для создания хэш-значения. Эти функции полезны при использовании класса коллекции для хранения данных на основе строки. Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) при с восприниматься в качестве ссылки на объекты string.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringElementTraitsI::CompareElements  
 Эта функция статических для сравнения двух строковых элементов на равенство, без учета различия регистра.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Первая строка элемента.  
  
 `str2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Сравнения без учета регистра.  
  
##  <a name="compareelementsordered"></a>CStringElementTraitsI::CompareElementsOrdered  
 Эта функция статических для сравнения двух строковых элементов, без учета различия регистра.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Первая строка элемента.  
  
 `str2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0="" if=""> `str1` — меньше, чем `str2`, или настроек 0, если `str1` больше, чем `str2`. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.  

  
### <a name="remarks"></a>Примечания  
 Сравнения без учета регистра.  
  
##  <a name="hash"></a>CStringElementTraitsI::Hash  
 Эта функция статических для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Элемент строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает хэш-значение, вычисляемое с использованием содержимого строки.  
  
##  <a name="inargtype"></a>CStringElementTraitsI::INARGTYPE  
 Тип данных для добавления элементов в объекте класса коллекции.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE  
 Тип данных, использовать для получения элементов из объекта класса коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)

