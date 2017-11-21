---
title: "Класс CStringElementTraitsI | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f2a2cbe93826ed2cad5d33d50df119d0ff5cb298
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов к такому объекту класса коллекции.|  
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Тип данных для использования для получения элементов из объекта класса коллекции.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](#compareelements)|Вызовите эту статическую функцию для сравнения двух строковых элементов на равенство, без учета различия регистра.|  
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Вызовите эту статическую функцию для сравнения двух строковых элементов, без учета различия регистра.|  
|[CStringElementTraitsI::Hash](#hash)|Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции для сравнения строк, а также для создания хэш-значения. Эти функции полезны при использовании класс коллекции для хранения данных на основе строки. Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) когда строковые объекты будут с обрабатываться как ссылки.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringElementTraitsI::CompareElements  
 Вызовите эту статическую функцию для сравнения двух строковых элементов на равенство, без учета различия регистра.  
  
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
 Вызовите эту статическую функцию для сравнения двух строковых элементов, без учета различия регистра.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Первая строка элемента.  
  
 `str2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0 Если `str1` — меньше, чем `str2`, или значение > 0, если `str1` больше, чем `str2`. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.  

  
### <a name="remarks"></a>Примечания  
 Сравнения без учета регистра.  
  
##  <a name="hash"></a>CStringElementTraitsI::Hash  
 Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Элемент строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение хэша, вычисленных с помощью содержимое строки.  
  
##  <a name="inargtype"></a>CStringElementTraitsI::INARGTYPE  
 Тип данных, используемый для добавления элементов к такому объекту класса коллекции.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE  
 Тип данных для использования для получения элементов из объекта класса коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)
