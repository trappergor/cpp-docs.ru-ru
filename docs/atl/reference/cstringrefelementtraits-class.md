---
title: Класс CStringRefElementTraits | Документация Майкрософт
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
ms.openlocfilehash: 967ae999811e829ae7a890d367a6cdc16fb28239
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880493"
---
# <a name="cstringrefelementtraits-class"></a>Класс CStringRefElementTraits
Этот класс предоставляет статические функции, связанные с строк, которые хранятся в объектах класса коллекции. Объекты-строки обрабатываются как ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Тип данных, хранимых в коллекции.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Вызовите эту статическую функцию для сравнения двух строковых элементов на предмет равенства.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Вызовите эту статическую функцию для сравнения двух элементов строки.|  
|[CStringRefElementTraits::Hash](#hash)|Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет статические функции для сравнения строк, а также для создания хэш-значение. Эти функции полезны при использовании класса коллекции для хранения строковых данных. В отличие от [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` вызывает `CString` аргументы нельзя передать как **const** `CString&` ссылки.  
  
 Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="compareelements"></a>  CStringRefElementTraits::CompareElements  
 Вызовите эту статическую функцию для сравнения двух строковых элементов на предмет равенства.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *element1*  
 Первая строка, элемент.  
  
 *элемент элемент2*  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если элементы равны; значение false в противном случае.  
  
##  <a name="compareelementsordered"></a>  CStringRefElementTraits::CompareElementsOrdered  
 Вызовите эту статическую функцию для сравнения двух элементов строки.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *str1*  
 Первая строка, элемент.  
  
 *str2*  
 Вторая строка элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Нуль, если строки идентичны, < 0 Если *str1* — меньше, чем *str2*, или > 0 Если *str1* больше, чем *str2*. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.  
  
##  <a name="hash"></a>  CStringRefElementTraits::Hash  
 Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *str*  
 Элемент строку.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает хэш-значение, вычисляемое с использованием содержимого строки.  
  
## <a name="see-also"></a>См. также  
 [Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
