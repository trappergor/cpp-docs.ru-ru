---
title: "Класс CStringElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CStringElementTraits<T>
- ATL::CStringElementTraits<T>
- CStringElementTraits
- ATL.CStringElementTraits
- ATL::CStringElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
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
ms.openlocfilehash: f46ff072bcd0f772dac1bba52b114d82ee433112
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraits-class"></a>Класс CStringElementTraits
Этот класс предоставляет статические функции, используемые классами коллекции хранения `CString` объектов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных, хранящихся в коллекции.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|Тип данных для добавления элементов в объекте класса коллекции.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Тип данных, использовать для получения элементов из объекта класса коллекции.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Статический) Эта функция используется для сравнения на равенство двух элементов строки.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Статический) Эта функция используется для сравнения двух элементов строки.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Статический) Эта функция вызывается для копирования `CString` элементов, хранящихся в объекте класса коллекции.|  
|[CStringElementTraits::Hash](#hash)|(Статический) Эта функция вызывается для вычисления хэш-значение для заданной строки элемента.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Статический) Эта функция вызывается для перемещения `CString` элементов, хранящихся в объекте класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции для копирования, перемещения и сравнения строк, а также для создания хэш-значения. Эти функции полезны при использовании класса коллекции для хранения данных на основе строки. Используйте [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) когда необходимы сравнения без учета регистра. Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) при будут восприниматься в качестве ссылки на объекты string.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** cstringt.h  
  
##  <a name="a-namecompareelementsa--cstringelementtraitscompareelements"></a><a name="compareelements"></a>CStringElementTraits::CompareElements  
 Эта функция статических для сравнения на равенство двух элементов строки.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Первая строка элемента.  
  
 `str2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны false в противном случае.  
  
##  <a name="a-namecompareelementsordereda--cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 Эта функция статических для сравнения двух элементов строки.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Первая строка элемента.  
  
 `str2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0="" if=""> `str1` — меньше, чем `str2`, или настроек 0, если `str1` больше, чем `str2`. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.  

  
##  <a name="a-namecopyelementsa--cstringelementtraitscopyelements"></a><a name="copyelements"></a>CStringElementTraits::CopyElements  
 Эта функция статических скопируйте `CString` элементов, хранящихся в объекте класса коллекции.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 Указатель на первый элемент, который получит скопированные данные.  
  
 `pSrc`  
 Указатель на первый элемент для копирования.  
  
 `nElements`  
 Число элементов для копирования.  
  
### <a name="remarks"></a>Примечания  
 Исходный и целевой элементы не должны перекрываться.  
  
##  <a name="a-namehasha--cstringelementtraitshash"></a><a name="hash"></a>CStringElementTraits::Hash  
 Эта функция статических для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Элемент строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает хэш-значение, вычисляемое с использованием содержимого строки.  
  
##  <a name="a-nameinargtypea--cstringelementtraitsinargtype"></a><a name="inargtype"></a>CStringElementTraits::INARGTYPE  
 Тип данных для добавления элементов в объекте класса коллекции.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cstringelementtraitsoutargtype"></a><a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 Тип данных, использовать для получения элементов из объекта класса коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="a-namerelocateelementsa--cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 Эта функция статических переместить `CString` элементов, хранящихся в объекте класса коллекции.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 Указатель на первый элемент, который получит перемещенный данные.  
  
 `pSrc`  
 Указатель на первый элемент для перемещения.  
  
 `nElements`  
 Число элементов для перемещения.  
  
### <a name="remarks"></a>Примечания  
 Эта статическая функция вызывает [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), которого достаточно для большинства типов данных. Перемещение объекты содержат указатели на свои собственные члены, эта статическая функция необходимо переопределить.  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Класс CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

