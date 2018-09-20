---
title: Класс CTypedPtrArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a83e425863afe4a8f355c4ce4543935c4e910216
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408018"
---
# <a name="ctypedptrarray-class"></a>CTypedPtrArray-класс

Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrArray` или `CObArray`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrArray : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс для класса массив типизированных указателей; должен быть класса массива ( `CObArray` или `CPtrArray`).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrArray::Add](#add)|Добавляет новый элемент в конец массива. Растет массива, при необходимости|
|[CTypedPtrArray::Append](#append)|Добавляет содержимое одного массива в конец другого. Растет массива, при необходимости|
|[CTypedPtrArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CTypedPtrArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CTypedPtrArray::GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CTypedPtrArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CTypedPtrArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[CTypedPtrArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[[CTypedPtrArray::operator]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

При использовании `CTypedPtrArray` вместо `CPtrArray` или `CObArray`, средство проверки типов C++ помогает устранить ошибки, вызванные типы несоответствие указателей.

Кроме того `CTypedPtrArray` оболочки выполняет большей части приведения, которое будет обязательным, если вы использовали `CObArray` или `CPtrArray`.

Так как все `CTypedPtrArray` функции, встроенные, использование этого шаблона незначительно повлиять на размер или скорость кода.

Дополнительные сведения об использовании `CTypedPtrArray`, см. в статьях [коллекций](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`CTypedPtrArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

##  <a name="add"></a>  CTypedPtrArray::Add

Эта функция-член вызывает `BASE_CLASS` **:: добавить**.

```
INT_PTR Add(TYPE newElement);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элемента, добавляемого в массив.

*newElement*<br/>
Элемент, добавляемый в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::Add](../../mfc/reference/cobarray-class.md#add).

##  <a name="append"></a>  CTypedPtrArray::Append

Эта функция-член вызывает `BASE_CLASS`:: Append **.

```
INT_PTR Append(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс для класса массив типизированных указателей; должен быть класса массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*src*<br/>
Источник элементов для добавления в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первый добавленный элемент.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::Append](../../mfc/reference/cobarray-class.md#append).

##  <a name="copy"></a>  CTypedPtrArray::Copy

Эта функция-член вызывает `BASE_CLASS` **:: копирования**.

```
void Copy(const CTypedPtrArray<BASE_CLASS, TYPE>& src);
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс для класса массив типизированных указателей; должен быть класса массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*src*<br/>
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::Copy](../../mfc/reference/cobarray-class.md#copy).

##  <a name="elementat"></a>  CTypedPtrArray::ElementAt

Это встраиваемая функция вызывает `BASE_CLASS` **:: ElementAt**.

```
TYPE& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в этом массиве.

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Возвращаемое значение

Временную ссылку на элемент в расположении, заданном параметром *nIndex*. Этот элемент является типа, указанного в параметре шаблона *тип*.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat).

##  <a name="getat"></a>  CTypedPtrArray::GetAt

Это встраиваемая функция вызывает `BASE_CLASS` **:: GetAt**.

```
TYPE GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, которые хранятся в массиве.

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `BASE_CLASS` **:: GetUpperBound**.

### <a name="return-value"></a>Возвращаемое значение

Копия элемента в расположении, указанном по *nIndex*. Этот элемент является типа, указанного в параметре шаблона *тип*.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)

##  <a name="insertat"></a>  CTypedPtrArray::InsertAt

Эта функция-член вызывает `BASE_CLASS` **:: InsertAt**.

```
void InsertAt(
    INT_PTR nIndex,
    TYPE newElement,
    INT_PTR nCount = 1);


void InsertAt(
    INT_PTR nStartIndex,
    CTypedPtrArray<BASE_CLASS, TYPE>* pNewArray);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который может быть больше, чем значение, возвращенное [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*newElement*<br/>
Указатель на объект, который следует поместить в этот массив. Объект *newElement* значения **NULL** разрешено.

*nCount*<br/>
Количество раз, когда этот элемент должен быть вставлен (по умолчанию — 1).

*nStartIndex*<br/>
Целочисленный индекс, который может быть больше, чем значение, возвращенное `CObArray::GetUpperBound`.

*BASE_CLASS*<br/>
Базовый класс для класса массив типизированных указателей; должен быть класса массива ( [CObArray](../../mfc/reference/cobarray-class.md) или [CPtrArray](../../mfc/reference/cptrarray-class.md)).

*pNewArray*<br/>
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat).

##  <a name="operator_at"></a>  [CTypedPtrArray::operator]

Эти встроенные операторы вызова `BASE_CLASS` **:: operator []**.

```
TYPE& operator[ ](int_ptr nindex);
TYPE operator[ ](int_ptr nindex) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, которые хранятся в массиве.

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `BASE_CLASS` **:: GetUpperBound**.

### <a name="remarks"></a>Примечания

Первый оператор, вызывается для массивов, которые не являются **const**, можно использовать на (r-значение) справа или слева от оператора присваивания (l значение). Вызвано второе, **const** массивы, может использоваться только в правой части.

Отладочная версия библиотеки утверждает, если индекс (либо слева или справа от оператора присваивания) выходит за границы.

##  <a name="setat"></a>  CTypedPtrArray::SetAt

Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.

```
void SetAt(
    INT_PTR nIndex,
    TYPE ptr);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное [CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound).

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*ptr*<br/>
Указатель на элемент, вставляемый в массиве, nIndex. Допускается значение NULL.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat).

##  <a name="setatgrow"></a>  CTypedPtrArray::SetAtGrow

Эта функция-член вызывает `BASE_CLASS` **:: SetAtGrow**.

```
void SetAtGrow(
    INT_PTR nIndex,
    TYPE newElement);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0.

*ТИП*<br/>
Тип элементов, хранящихся в массиве базового класса.

*newElement*<br/>
Указатель на объект, добавляемый в этот массив. Объект **NULL** допустимое значение.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow).

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPtrArray](../../mfc/reference/cptrarray-class.md)<br/>
[Класс CObArray](../../mfc/reference/cobarray-class.md)
