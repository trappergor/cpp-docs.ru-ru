---
title: Класс CStringRefElementTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8746bf216be417fb569aae58421b272c983914b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360691"
---
# <a name="cstringrefelementtraits-class"></a>Класс CStringRefElementTraits
Этот класс предоставляет статические функции, связанные с строк, хранящихся в коллекции объектов класса. Строковые объекты обрабатываются как ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Вызовите эту статическую функцию для сравнения двух строковых элементов на равенство.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Вызовите эту статическую функцию для сравнения двух строковых элементов.|  
|[CStringRefElementTraits::Hash](#hash)|Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции для сравнения строк, а также для создания хэш-значения. Эти функции полезны при использовании класс коллекции для хранения данных на основе строки. В отличие от [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` вызывает `CString` аргументы для передачи как **const CString &** ссылки.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="compareelements"></a>  CStringRefElementTraits::CompareElements  
 Вызовите эту статическую функцию для сравнения двух строковых элементов на равенство.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `element1`  
 Первая строка элемента.  
  
 `element2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны false в противном случае.  
  
##  <a name="compareelementsordered"></a>  CStringRefElementTraits::CompareElementsOrdered  
 Вызовите эту статическую функцию для сравнения двух строковых элементов.  
  
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
  
##  <a name="hash"></a>  CStringRefElementTraits::Hash  
 Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Элемент строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение хэша, вычисленных с помощью содержимое строки.  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
