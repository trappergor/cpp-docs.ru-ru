---
title: "Класс CStringElementTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
dev_langs: C++
helpviewer_keywords: CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 025c9aa66a8647fd5d8ca9803aedb50b27ed3be1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|Тип данных, используемый для добавления элементов к такому объекту класса коллекции.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Тип данных для использования для получения элементов из объекта класса коллекции.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Статический) Вызывайте эту функцию для сравнения двух строковых элементов на равенство.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Статический) Вызывайте эту функцию для сравнения двух строковых элементов.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Статический) Эта функция вызывается для копирования `CString` элементов, хранящихся в объекте класса коллекции.|  
|[CStringElementTraits::Hash](#hash)|(Статический) Эта функция вызывается для вычисления хэш-значение для заданной строки элемента.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Статический) Вызывайте эту функцию, чтобы переместить `CString` элементов, хранящихся в объекте класса коллекции.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс содержит статические функции для копирования, перемещения и сравнение строк, а также для создания хэш-значения. Эти функции полезны при использовании класс коллекции для хранения данных на основе строки. Используйте [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) когда необходимы сравнения без учета регистра. Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) когда строковые объекты будут обработаны как ссылки.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** cstringt.h  
  
##  <a name="compareelements"></a>CStringElementTraits::CompareElements  
 Вызовите эту статическую функцию для сравнения двух строковых элементов на равенство.  
  
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
  
##  <a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 Вызовите эту статическую функцию для сравнения двух строковых элементов.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Параметры  
 `str1`  
 Первая строка элемента.  
  
 `str2`  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0 Если `str1` — меньше, чем `str2`, или значение > 0, если `str1` больше, чем `str2`. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.  

  
##  <a name="copyelements"></a>CStringElementTraits::CopyElements  
 Вызовите эту статическую функцию, чтобы скопировать `CString` элементов, хранящихся в объекте класса коллекции.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Параметры  
 `pDest`  
 Указатель на первый элемент, который получит копируемых данных.  
  
 `pSrc`  
 Указатель на первый элемент для копирования.  
  
 `nElements`  
 Число элементов для копирования.  
  
### <a name="remarks"></a>Примечания  
 Исходный и целевой элементы не должны перекрываться.  
  
##  <a name="hash"></a>CStringElementTraits::Hash  
 Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Элемент строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение хэша, вычисленных с помощью содержимое строки.  
  
##  <a name="inargtype"></a>CStringElementTraits::INARGTYPE  
 Тип данных, используемый для добавления элементов к такому объекту класса коллекции.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 Тип данных для использования для получения элементов из объекта класса коллекции.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 Вызовите эту статическую функцию, чтобы переместить `CString` элементов, хранящихся в объекте класса коллекции.  
  
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
 Указатель на первый элемент в другое место.  
  
 `nElements`  
 Количество элементов в другое место.  
  
### <a name="remarks"></a>Примечания  
 Эта статическая функция вызывает [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), что вполне достаточно для большинства типов данных. Объекты перемещения содержат указатели на свои собственные члены, эта статическая функция необходимо переопределить.  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Класс CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
