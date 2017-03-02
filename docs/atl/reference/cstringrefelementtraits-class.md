---
title: "Класс CStringRefElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATL.CStringRefElementTraits
- ATL::CStringRefElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
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
ms.openlocfilehash: 3709a5d4aac02651e5b6fafd441499fea1f8eabc
ms.lasthandoff: 02/24/2017

---
# <a name="cstringrefelementtraits-class"></a>Класс CStringRefElementTraits
Этот класс предоставляет статические функции, связанные с строк, хранящихся в коллекции объектов класса. Объекты-строки обрабатываются как ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранящихся в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Эта функция статических для сравнения на равенство двух элементов строки.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Эта функция статических для сравнения двух элементов строки.|  
|[CStringRefElementTraits::Hash](#hash)|Эта функция статических для вычисления хэш-значение для заданной строки элемента.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции для сравнения строк, а также для создания хэш-значения. Эти функции полезны при использовании класса коллекции для хранения данных на основе строки. В отличие от [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` вызывает `CString` аргументы для передачи в качестве **const CString &** ссылки.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="a-namecompareelementsa--cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 Эта функция статических для сравнения на равенство двух элементов строки.  
  
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
  
##  <a name="a-namecompareelementsordereda--cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 Эта функция статических для сравнения двух элементов строки.  
  
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
  
##  <a name="a-namehasha--cstringrefelementtraitshash"></a><a name="hash"></a>CStringRefElementTraits::Hash  
 Эта функция статических для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Элемент строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает хэш-значение, вычисляемое с использованием содержимого строки.  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

