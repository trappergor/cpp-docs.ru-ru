---
title: Класс CStringRefElementTraits
ms.date: 11/04/2016
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
ms.openlocfilehash: b4dd76b9592b255a1553be3ca7a249f58fb2672e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330585"
---
# <a name="cstringrefelementtraits-class"></a>Класс CStringRefElementTraits

Этот класс предоставляет статические функции, связанные со строками, хранящимися в объектах класса коллекции. Объекты строки рассматриваются в качестве ссылок.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных, которые будут храниться в коллекции.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStringRefElementTraits:CompareElements](#compareelements)|Вызовите эту статическую функцию, чтобы сравнить два элемента строки для равенства.|
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Вызовите эту статическую функцию, чтобы сравнить два элемента строки.|
|[CStringRefElementTraits::Хэш](#hash)|Вызовите эту статическую функцию, чтобы вычислить значение хэша для данного элемента строки.|

## <a name="remarks"></a>Remarks

Этот класс предоставляет статические функции для сравнения строк и для создания значения хэша. Эти функции полезны при использовании класса сбора для хранения строковых данных. В отличие от [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) и [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` вызывает `CString` аргументы, которые должны быть переданы в качестве **const** `CString&` ссылки.

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>CStringRefElementTraits:CompareElements

Вызовите эту статическую функцию, чтобы сравнить два элемента строки для равенства.

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>Параметры

*элемент1*<br/>
Первый элемент строки.

*элемент2*<br/>
Второй элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если элементы равны, ложные в противном случае.

## <a name="cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered

Вызовите эту статическую функцию, чтобы сравнить два элемента строки.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первый элемент строки.

*str2*<br/>
Второй элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Ноль, если строки идентичны, < 0, если *str1* меньше, чем *str2,* или > 0, если *str1* больше, чем *str2.* Для выполнения сравнений используется метод [CStringT::Compare.](../../atl-mfc-shared/reference/cstringt-class.md#compare)

## <a name="cstringrefelementtraitshash"></a><a name="hash"></a>CStringRefElementTraits::Хэш

Вызовите эту статическую функцию, чтобы вычислить значение хэша для данного элемента строки.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Элемент строки.

### <a name="return-value"></a>Возвращаемое значение

Возвращает хэш-значение, рассчитанное с использованием содержимого строки.

## <a name="see-also"></a>См. также раздел

[Класс CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
