---
title: Класс CDefaultCompareTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1aecfcb493bfc35e0d6f059c296af1b358eee93f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103220"
---
# <a name="cdefaultcomparetraits-class"></a>Класс CDefaultCompareTraits

Этот класс предоставляет по умолчанию элемент функции сравнения.

## <a name="syntax"></a>Синтаксис

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Статический) Вызывайте эту функцию для сравнения двух элементов на предмет равенства.|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Статический) Вызывайте эту функцию, чтобы определить элемент больше и меньше.|

## <a name="remarks"></a>Примечания

Этот класс содержит два статических функций для сравнения элементов, сохраненную в объекте класса коллекции. Этот класс используется [класс CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md).

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements

Вызывайте эту функцию для сравнения двух элементов на предмет равенства.

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>Параметры

*element1*<br/>
Первый элемент

*элемент элемент2*<br/>
Второй элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если элементы равны; значение false в противном случае.

### <a name="remarks"></a>Примечания

По умолчанию эта функция реализуется равенство (**==**) оператор. Для объектов, отличных от простых типов данных эта функция может потребоваться переопределить.

##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered

Вызывайте эту функцию, чтобы определить элемент больше и меньше.

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>Параметры

*element1*<br/>
Первый элемент

*элемент элемент2*<br/>
Второй элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает целое число, согласно приведенной ниже таблице:

|Условие|Возвращаемое значение|
|---------------|------------------|
|*element1* < *элемент элемент2*|<0|
|*element1* == *элемент элемент2*|0|
|*element1* > *элемент элемент2*|>0|

### <a name="remarks"></a>Примечания

Реализация по умолчанию эта функция использует **==**, **\<**, и **>** операторы. Для объектов, отличных от простых типов данных эта функция может потребоваться переопределить.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
