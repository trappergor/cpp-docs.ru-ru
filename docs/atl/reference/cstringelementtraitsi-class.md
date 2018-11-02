---
title: Класс CStringElementTraitsI
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 35215546268c4c48f913e7aef763768fffc76d59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551727"
---
# <a name="cstringelementtraitsi-class"></a>Класс CStringElementTraitsI

Этот класс предоставляет статические функции, связанные с строк, которые хранятся в объектах класса коллекции. Это похоже на [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), но выполняет сравнение без учета регистра.

## <a name="syntax"></a>Синтаксис

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, хранимых в коллекции.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringElementTraitsI::CompareElements](#compareelements)|Вызовите эту статическую функцию для сравнения двух строковых элементов на предмет равенства, без учета различий в регистре.|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Вызовите эту статическую функцию для сравнения двух строковых элементов, без учета различий в регистре.|
|[CStringElementTraitsI::Hash](#hash)|Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.|

## <a name="remarks"></a>Примечания

Этот класс предоставляет статические функции для сравнения строк, а также для создания хэш-значение. Эти функции полезны при использовании класса коллекции для хранения строковых данных. Используйте [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) при с восприниматься в качестве ссылки на объекты-строки.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="compareelements"></a>  CStringElementTraitsI::CompareElements

Вызовите эту статическую функцию для сравнения двух строковых элементов на предмет равенства, без учета различий в регистре.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первая строка, элемент.

*str2*<br/>
Вторая строка элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если элементы равны; значение false в противном случае.

### <a name="remarks"></a>Примечания

Сравнения нечувствительны к регистру.

##  <a name="compareelementsordered"></a>  CStringElementTraitsI::CompareElementsOrdered

Вызовите эту статическую функцию для сравнения двух строковых элементов, без учета различий в регистре.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первая строка, элемент.

*str2*<br/>
Вторая строка элемента.

### <a name="return-value"></a>Возвращаемое значение

Нуль, если строки идентичны, < 0 Если *str1* — меньше, чем *str2*, или > 0 Если *str1* больше, чем *str2*. [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) метод используется для выполнения сравнений.

### <a name="remarks"></a>Примечания

Сравнения нечувствительны к регистру.

##  <a name="hash"></a>  CStringElementTraitsI::Hash

Вызовите эту статическую функция для вычисления хэш-значение для заданной строки элемента.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Параметры

*str*<br/>
Элемент строку.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение, вычисляемое с использованием содержимого строки.

##  <a name="inargtype"></a>  CStringElementTraitsI::INARGTYPE

Тип данных, который нужно использовать для добавления элементов в объекте класса коллекции.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraitsI::OUTARGTYPE

Тип данных, который нужно использовать для извлечения элементов из объекта класса коллекции.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>См. также

[Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)<br/>
[Класс CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)
