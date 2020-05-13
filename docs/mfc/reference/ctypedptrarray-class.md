---
title: Класс CTypedPtrArray
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrArray
- AFXTEMPL/CTypedPtrArray
- AFXTEMPL/CTypedPtrArray::Add
- AFXTEMPL/CTypedPtrArray::Append
- AFXTEMPL/CTypedPtrArray::Copy
- AFXTEMPL/CTypedPtrArray::ElementAt
- AFXTEMPL/CTypedPtrArray::GetAt
- AFXTEMPL/CTypedPtrArray::InsertAt
- AFXTEMPL/CTypedPtrArray::SetAt
- AFXTEMPL/CTypedPtrArray::SetAtGrow
helpviewer_keywords:
- CTypedPtrArray [MFC], Add
- CTypedPtrArray [MFC], Append
- CTypedPtrArray [MFC], Copy
- CTypedPtrArray [MFC], ElementAt
- CTypedPtrArray [MFC], GetAt
- CTypedPtrArray [MFC], InsertAt
- CTypedPtrArray [MFC], SetAt
- CTypedPtrArray [MFC], SetAtGrow
ms.assetid: e3ecdf1a-a889-4156-92dd-ddbd36ccd919
ms.openlocfilehash: 20cf147e955b6b19919f35750b0f46a8b5a67ad0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752064"
---
# <a name="ctypedptrarray-class"></a>Класс CTypedPtrArray

Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrArray` или `CObArray`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс типа массива набранных указателей; должен быть класс `CObArray` массива (или). `CPtrArray`

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrArray:Добавить](#add)|Добавляет новый элемент в конец массива. Растет массив при необходимости|
|[CTypedPtrArray::Приложение](#append)|Добавляет содержимое одного массива в конец другого. Растет массив при необходимости|
|[CTypedPtrArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CTypedPtrArray::ЭлементАт](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CTypedPtrArray::GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CTypedPtrArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CTypedPtrArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrArray::оператор \[\]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Remarks

При `CTypedPtrArray` использовании, `CPtrArray` `CObArray`а не в том, что объект проверки типа СЗ помогает устранить ошибки, вызванные несовместимыми типами указателей.

Кроме того, `CTypedPtrArray` обертка выполняет большую часть литья, `CObArray` `CPtrArray`которые будут необходимы, если вы использовали или .

Поскольку `CTypedPtrArray` все функции являются внеочередными, использование этого шаблона не оказывает существенного влияния на размер или скорость кода.

Для получения дополнительной `CTypedPtrArray`информации об [Template-Based Classes](../../mfc/template-based-classes.md)использовании , [см.](../../mfc/collections.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="ctypedptrarrayadd"></a><a name="add"></a>CTypedPtrArray:Добавить

Эта функция `BASE_CLASS`участника **вызывает::Добавить**.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элемента, который будет добавлен в массив.

*newElement*<br/>
Элемент, который будет добавлен в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::Добавить](../../mfc/reference/cobarray-class.md#add).

## <a name="ctypedptrarrayappend"></a><a name="append"></a>CTypedPtrArray::Приложение

Эта функция `BASE_CLASS`участника вызывает::Приложение.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс типа массива набранных указателей; должен быть класс массива [(CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*src*<br/>
Источник элементов, которые будут приписаны к массиву.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого придативного элемента.

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::Приложение](../../mfc/reference/cobarray-class.md#append).

## <a name="ctypedptrarraycopy"></a><a name="copy"></a>CTypedPtrArray::Copy

Эта функция `BASE_CLASS`участника **вызывает::Copy**.

```cpp
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс типа массива набранных указателей; должен быть класс массива [(CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*src*<br/>
Источник элементов, которые должны быть скопированы в массив.

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::Copy](../../mfc/reference/cobarray-class.md#copy).

## <a name="ctypedptrarrayelementat"></a><a name="elementat"></a>CTypedPtrArray::ЭлементАт

Эта вливая функция вызывает `BASE_CLASS` **::ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в этом массиве.

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем `BASE_CLASS`или равен значению, **возвращенному::GetUpperBound**.

### <a name="return-value"></a>Возвращаемое значение

Временная ссылка на элемент в месте, указанном *nIndex.* Этот элемент является типом, указанным параметром шаблона *TYPE.*

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::Elementat](../../mfc/reference/cobarray-class.md#elementat).

## <a name="ctypedptrarraygetat"></a><a name="getat"></a>CTypedPtrArray::GetAt

Эта влиневая функция вызывает `BASE_CLASS` **::GetAt**.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в массиве.

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем `BASE_CLASS`или равен значению, **возвращенному::GetUpperBound**.

### <a name="return-value"></a>Возвращаемое значение

Копия элемента в месте, указанном *nIndex*. Этот элемент является типом, указанным параметром шаблона *TYPE.*

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::GetAt](../../mfc/reference/cobarray-class.md#getat)

## <a name="ctypedptrarrayinsertat"></a><a name="insertat"></a>CTypedPtrArray::InsertAt

Эта функция `BASE_CLASS`участника **вызывает ::InsertAt**.

```cpp
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Целый индекс, который может быть больше, чем значение, возвращенное [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*newElement*<br/>
Указатель объекта, который будет размещен в этом массиве. Допускается *новыйэлемент* стоимости **NULL.**

*Ncount*<br/>
Количество раз, когда этот элемент должен быть вставлен (по умолчанию до 1).

*nСтарт-индекс*<br/>
Индекс, который может быть больше, чем `CObArray::GetUpperBound`значение, возвращенное .

*BASE_CLASS*<br/>
Базовый класс типа массива набранных указателей; должен быть класс массива [(CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*pNewArray*<br/>
Другой массив, содержащий элементы, которые будут добавлены в этот массив.

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::Insertat](../../mfc/reference/cobarray-class.md#insertat).

## <a name="ctypedptrarrayoperator--"></a><a name="operator_at"></a>CTypedPtrArray::оператор

Эти вливые операторы называют `BASE_CLASS` **::оператор .**

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов, хранящихся в массиве.

*Nindex*<br/>
Равный индекс, который больше или равен 0 и меньше, чем `BASE_CLASS`или равен значению, **возвращенному::GetUpperBound**.

### <a name="remarks"></a>Remarks

Первый оператор, называемый массивами, которые не являются **конст,** может быть использован либо справа (r-value) или слева (l-значение) оператора назначения. Второй, на который ссылается для **конст-массивов,** может быть использован только справа.

Версия библиотеки Debug утверждает, что подтекст (или слева, либо справа от оператора назначения) выходит за рамки.

## <a name="ctypedptrarraysetat"></a><a name="setat"></a>CTypedPtrArray::SetAt

Эта функция `BASE_CLASS`участника **вызывает ::SetAt**.

```cpp
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Целый индекс, который больше, чем или равный 0 и меньше, чем или равные значения вернулся [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*Ptr*<br/>
Указатель на элемент, который будет вставлен в массив в nIndex. Допускается значение NULL.

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. CobArray::SetAt](../../mfc/reference/cobarray-class.md#setat).

## <a name="ctypedptrarraysetatgrow"></a><a name="setatgrow"></a>CTypedPtrArray::SetAtGrow

Эта функция `BASE_CLASS`участника **вызывает ::SetatGrow**.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Равный индекс, который больше или равен 0.

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*newElement*<br/>
Указатель объекта, который будет добавлен в этот массив. Допускается **значение NULL.**

### <a name="remarks"></a>Remarks

Для более подробных замечаний, [см. Cobarray::SetatGrow](../../mfc/reference/cobarray-class.md#setatgrow).

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPtrArray](../../mfc/reference/cptrarray-class.md)<br/>
[Класс CObArray](../../mfc/reference/cobarray-class.md)
