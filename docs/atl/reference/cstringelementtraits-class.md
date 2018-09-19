---
title: Класс CStringElementTraits | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2359bb3909c803e4df1efdeef9058a3553908ff9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074062"
---
# <a name="cstringelementtraits-class"></a>Класс CStringElementTraits

Этот класс предоставляет статические функции, используемые классами коллекцию хранения `CString` объектов.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(Статический) Вызывайте эту функцию для сравнения двух строковых элементов на предмет равенства.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Статический) Вызывайте эту функцию для сравнения двух строковых элементов.|
|[CStringElementTraits::CopyElements](#copyelements)|(Статический) Вызывайте эту функцию, чтобы скопировать `CString` элементов, сохраненную в объекте класса коллекции.|
|[CStringElementTraits::Hash](#hash)|(Статический) Вызывайте эту функцию для вычисления хэш-значение для заданной строки элемента.|
|[CStringElementTraits::RelocateElements](#relocateelements)|(Статический) Вызывайте эту функцию, чтобы переместить `CString` элементов, сохраненную в объекте класса коллекции.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции для копирования, перемещения и сравнения строк, а также для создания хэш-значение. Эти функции полезны при использовании класса коллекции для хранения строковых данных. Используйте [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) когда необходимы сравнения без учета регистра. Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) когда строка объекты должны восприниматься в качестве ссылки.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** cstringt.h

##  <a name="compareelements"></a>  CStringElementTraits::CompareElements

Вызовите эту статическую функцию для сравнения двух строковых элементов на предмет равенства.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первая строка, элемент.

*str2*<br/>
Вторая строка элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если элементы равны; значение false в противном случае.

##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered

Вызовите эту статическую функцию для сравнения двух элементов строки.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первая строка, элемент.

*str2*<br/>
Вторая строка элемента.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0 Если *str1* — меньше, чем *str2*, или > 0 Если *str1* больше, чем *str2*. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.  

##  <a name="copyelements"></a>  CStringElementTraits::CopyElements

Вызовите эту статическую функцию, чтобы скопировать `CString` элементов, сохраненную в объекте класса коллекции.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
Указатель на первый элемент, который будет отправляться скопированные данные.

*pSrc*<br/>
Указатель на первый элемент, для копирования.

*nElements*<br/>
Число элементов для копирования.

### <a name="remarks"></a>Примечания

Исходный и целевой элементы не должны перекрываться.

##  <a name="hash"></a>  CStringElementTraits::Hash

Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Элемент строку.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение, вычисляемое с использованием содержимого строки.

##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE

Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE

Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements

Вызовите эту статическую функцию, чтобы переместить `CString` элементов, сохраненную в объекте класса коллекции.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Параметры

*pDest*<br/>
Указатель на первый элемент, который будет получать перемещенные данные.

*pSrc*<br/>
Указатель на первый элемент, чтобы переместить.

*nElements*<br/>
Число элементов для перемещения.

### <a name="remarks"></a>Примечания

Вызывает эту статическую функцию [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), что вполне достаточно для большинства типов данных. Если перемещаемый объекты содержат указатели на свои собственные члены, эту статическую функцию необходимо переопределить.

## <a name="see-also"></a>См. также

[Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Класс CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
