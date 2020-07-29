---
title: Класс Кобаррай
ms.date: 11/04/2016
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
ms.openlocfilehash: b083bf0e82f9d9b928e613f07a71d36147240cd2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212375"
---
# <a name="cobarray-class"></a>Класс Кобаррай

Поддерживает массивы указателей `CObject` .

## <a name="syntax"></a>Синтаксис

```
class CObArray : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кобаррай:: Кобаррай](#cobarray)|Конструирует пустой массив для `CObject` указателей.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кобаррай:: Add](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[Кобаррай:: Append](#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|
|[Кобаррай:: Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[Кобаррай:: ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[Кобаррай:: Фриекстра](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[Кобаррай:: GetAt](#getat)|Возвращает значение по указанному индексу.|
|[Кобаррай:: NOCOUNT](#getcount)|Возвращает количество элементов в массиве.|
|[Кобаррай:: GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[Кобаррай:: DataSize](#getsize)|Возвращает количество элементов в массиве.|
|[Кобаррай:: GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[Кобаррай:: Инсертат](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[Кобаррай:: IsEmpty](#isempty)|Определяет, пуст ли массив.|
|[Кобаррай:: RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[Кобаррай:: RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[Кобаррай:: SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[Кобаррай:: Сетатгров](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[Кобаррай:: SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Кобаррай:: operator \[\]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Remarks

Эти массивы объектов похожи на массивы C, но они могут динамически сжиматься и увеличиваться по мере необходимости.

Индексы массивов всегда начинаются в позиции 0. Вы можете решить, следует ли исправить верхнюю границу или разрешить массиву расширять при добавлении элементов после текущей границы. Память выделяется непрерывно с верхней границей, даже если некоторые элементы имеют значение null.

В Win32 размер `CObArray` объекта ограничен только доступной памятью.

Как и в случае с массивом C, время доступа для `CObArray` индексированного элемента является константой и не зависит от размера массива.

`CObArray`включает макрос IMPLEMENT_SERIAL для поддержки сериализации и дампа его элементов. Если массив `CObject` указателей хранится в архиве с перегруженным оператором вставки или с `Serialize` функцией-членом, каждый `CObject` элемент в свою очередь сериализуется вместе с индексом массива.

Если требуется дамп отдельных `CObject` элементов в массиве, необходимо задать `CDumpContext` для глубины объекта значение 1 или больше.

При `CObArray` удалении объекта или удалении его элементов `CObject` удаляются только указатели, а не объекты, на которые они ссылаются.

> [!NOTE]
> Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Наследование класса массива аналогично наследованию списка. Дополнительные сведения о наследовании класса списков специального назначения см. в статье [коллекции](../../mfc/collections.md)статей.

> [!NOTE]
> Если предполагается сериализовать массив, необходимо использовать макрос IMPLEMENT_SERIAL в реализации производного класса.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

## <a name="cobarrayadd"></a><a name="add"></a>Кобаррай:: Add

Добавляет новый элемент в конец массива, увеличивая массив на 1.

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Параметры

*невелемент*<br/>
`CObject`Указатель, добавляемый к этому массиву.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Remarks

Если параметр [SetSize](#setsize) использовался со значением *нгровби* больше 1, может быть выделен дополнительный объем памяти. Однако верхняя граница будет увеличена только до 1.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::Add` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR добавить (байт** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR добавить (DWORD** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Добавление INT_PTR (void** <strong>\*</strong> `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR добавить (LPCTSTR** `newElement` **); Throw (CMemoryException \* );**<br /><br /> **Добавление INT_PTR (const CString&** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Add (uint** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR добавить (Word** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a>Кобаррай:: Append

Вызовите эту функцию члена, чтобы добавить содержимое другого массива в конец заданного массива.

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, добавляемых в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого добавленного элемента.

### <a name="remarks"></a>Remarks

Массивы должны быть одного типа.

При необходимости `Append` может выделить дополнительный объем памяти для размещения элементов, добавляемых в массив.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::Append` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR Append (const CByteArray&** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Append (const кдвордаррай&** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Append (const кптраррай&** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Append (const кстрингаррай&** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Append (const куинтаррай&** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR Append (const квордаррай&** *src* **);**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a>Кобаррай:: Copy

Вызовите эту функцию члена, чтобы перезаписать элементы заданного массива элементами другого массива того же типа.

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Remarks

`Copy`не освобождает память; Однако при необходимости `Copy` может выделить дополнительный объем памяти для размещения элементов, копируемых в массив.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::Copy` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void Copy (const CByteArray&** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void Copy (const кдвордаррай&** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void Copy (const кптраррай&** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void Copy (const кстрингаррай&** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void Copy (const куинтаррай&** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void Copy (const квордаррай&** *src* **);**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a>Кобаррай:: Кобаррай

Конструирует пустой `CObject` массив указателей.

```
CObArray();
```

### <a name="remarks"></a>Remarks

Массив растет по одному элементу за раз.

В следующей таблице показаны другие конструкторы, аналогичные `CObArray::CObArray` .

|Class|Конструктор|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Кдвордаррай ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Кптраррай ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Кстрингаррай ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Куинтаррай ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Квордаррай ();**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a>Кобаррай:: ElementAt

Возвращает временную ссылку на указатель элемента в массиве.

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `CObject` указатель.

### <a name="remarks"></a>Remarks

Он используется для реализации оператора присваивания слева для массивов. Обратите внимание, что это расширенная функция, которая должна использоваться только для реализации специальных операторов массивов.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::ElementAt` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE& ElementAt (INT_PTR** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& ElementAt (INT_PTR** `nIndex` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void \*& ElementAt (INT_PTR** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& ElementAt (INT_PTR** `nIndex` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& ElementAt (INT_PTR** `nIndex` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& ElementAt (INT_PTR** `nIndex` **);**|

### <a name="example"></a>Пример

  См. пример для [кобаррай:: DataSize](#getsize).

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a>Кобаррай:: Фриекстра

Освобождает все дополнительные памяти, которые были выделены, пока массив был увеличен.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Remarks

Эта функция не влияет на размер или верхнюю границу массива.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::FreeExtra` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void Фриекстра ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void Фриекстра ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void Фриекстра ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void Фриекстра ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void Фриекстра ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void Фриекстра ();**|

### <a name="example"></a>Пример

  См. пример для [кобаррай:: GetData](#getdata).

## <a name="cobarraygetat"></a><a name="getat"></a>Кобаррай:: GetAt

Возвращает элемент массива по указанному индексу.

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

### <a name="return-value"></a>Возвращаемое значение

`CObject`Элемент указателя, находящегося в данный момент в этом индексе.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Передача отрицательного значения или значения, превышающего значение, возвращенное, `GetUpperBound` приведет к неудачному утверждению.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetAt` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Byte GetAt (INT_PTR** `nIndex` **) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void \* GetAt (INT_PTR** `nIndex` **) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Uint GetAt (INT_PTR** `nIndex` **) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Слово GetAt (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a>Кобаррай:: NOCOUNT

Возвращает число элементов массива.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в массиве. Поскольку индексы отсчитываются от нуля, размер равен 1 больше, чем самый крупный индекс.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetCount` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR вычислить const ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR вычислить const ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR вычислить const ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR вычислить const ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR вычислить const ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR вычислить const ();**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a>Кобаррай:: GetData

Используйте эту функцию члена для получения прямого доступа к элементам в массиве.

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив `CObject` указателей.

### <a name="remarks"></a>Remarks

Если нет доступных элементов, `GetData` возвращает значение null.

Хотя прямой доступ к элементам массива позволяет быстрее работать, следует соблюдать осторожность при вызове `GetData` . любые ошибки, которые вы вносите непосредственно, влияют на элементы массива.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetData` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const BYTE \* GetData () const; BYTE \* GetData ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD \* GetData () const; DWORD \* GetData ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const void \* \* GetData () const; void \* \* GetData ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const \* -GetData () const в CString; Метод \* GetData в CString ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT \* GetData () const; UINT \* GetData ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD \* GetData () const; WORD \* GetData ();**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a>Кобаррай:: DataSize

Возвращает размер массива.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Remarks

Так как индексы отсчитываются от нуля, размер равен 1 больше, чем самый крупный индекс.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetSize` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR-size () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR-size () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR-size () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR-size () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR-size () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR-size () const;**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a>Кобаррай:: GetUpperBound

Возвращает текущую верхнюю границу данного массива.

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс верхней границы (от нуля).

### <a name="remarks"></a>Remarks

Поскольку индексы массива отсчитываются от нуля, эта функция возвращает значение 1, меньшее `GetSize` .

Условие `GetUpperBound( )` =-1 указывает, что массив не содержит элементов.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::GetUpperBound` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetUpperBound () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetUpperBound () const;**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a>Кобаррай:: Инсертат

Вставляет элемент (или все элементы в другом массиве) по указанному индексу.

```cpp
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который может быть больше значения, возвращаемого методом `GetUpperBound` .

*невелемент*<br/>
`CObject`Указатель, помещаемый в этот массив. Допускается *невелемент* значения NULL.

*нкаунт*<br/>
Количество раз, когда этот элемент должен быть вставлен (значение по умолчанию — 1).

*нстартиндекс*<br/>
Целочисленный индекс, который может быть больше значения, возвращаемого методом `GetUpperBound` .

*пневаррай*<br/>
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Remarks

Первая версия `InsertAt` вставляет один элемент (или несколько копий элемента) по указанному индексу в массиве. В процессе он смещается (путем увеличения индекса) существующего элемента в этом индексе и сдвигает все элементы над ним.

Вторая версия вставляет все элементы из другой `CObArray` коллекции, начиная с позиции *нстартиндекс* .

`SetAt`Функция, напротив, заменяет один указанный элемент массива и не сдвигает ни одного элемента.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::InsertAt` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void инсертат (INT_PTR** `nIndex` **, Byte** `newElement` **, int** `nCount` **= 1);**<br /><br /> **Throw (CMemoryException \* );**<br /><br /> **void инсертат (INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void инсертат (INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **Throw (CMemoryException \* );**<br /><br /> **void инсертат (INT_PTR** `nStartIndex` **, кдвордаррай** <strong>\*</strong> `pNewArray` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void инсертат (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **, int** `nCount` **= 1);**<br /><br /> **Throw (CMemoryException \* );**<br /><br /> **void инсертат (INT_PTR** `nStartIndex` **, кптраррай** <strong>\*</strong> `pNewArray` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void инсертат (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1);**<br /><br /> **Throw (CMemoryException \* );**<br /><br /> **void инсертат (INT_PTR** `nStartIndex` **, кстрингаррай** <strong>\*</strong> `pNewArray` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void инсертат (INT_PTR** `nIndex` **, uint** `newElement` **, int** `nCount` **= 1);**<br /><br /> **Throw (CMemoryException \* );**<br /><br /> **void инсертат (INT_PTR** `nStartIndex` **, куинтаррай** <strong>\*</strong> `pNewArray` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void инсертат (INT_PTR** `nIndex` **, Word** `newElement` **, int** `nCount` **= 1);**<br /><br /> **Throw (CMemoryException \* );**<br /><br /> **void инсертат (INT_PTR** `nStartIndex` **, квордаррай** <strong>\*</strong> `pNewArray` **);**<br /><br /> **Throw (CMemoryException \* );**|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a>Кобаррай:: IsEmpty

Определяет, пуст ли массив.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если массив пуст; в противном случае — 0.

## <a name="cobarrayoperator--"></a><a name="operator_at"></a>Кобаррай:: operator []

Эти операторы подстрочных индексов являются удобным заменой для `SetAt` `GetAt` функций и.

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Remarks

Первый оператор, вызываемый для массивов, не являющихся **`const`** , может использоваться либо справа (r-Value), либо слева (l-значение) оператора присваивания. Второй метод, который вызывается для **`const`** массивов, может использоваться только справа.

Отладочная версия библиотеки утверждает, находится ли индекс (в левой или правой части инструкции присваивания) вне границ.

В следующей таблице показаны другие операторы, аналогичные `CObArray::operator []` .

|Class|Оператор|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE& оператор [] (INT_PTR** `nindex` ** \) ;**<br /><br /> **Byte-оператор [] (INT_PTR** `nindex` ** \) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& operator [] (INT_PTR** `nindex` ** \) ;**<br /><br /> **DWORD-оператор [] (INT_PTR** `nindex` ** \) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void \*& operator [] (INT_PTR** `nindex` ** \) ;**<br /><br /> **void \* operator [] (INT_PTR** `nindex` ** \) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString& operator [] (INT_PTR** `nindex` ** \) ;**<br /><br /> **CString-оператор [] (INT_PTR** `nindex` ** \) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& operator [] (INT_PTR** `nindex` ** \) ;**<br /><br /> **Uint-оператор [] (INT_PTR** `nindex` ** \) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Слово& operator [] (INT_PTR** `nindex` ** \) ;**<br /><br /> **Слово operator [] (INT_PTR** `nindex` ** \) const;**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a>Кобаррай:: RemoveAll

Удаляет все указатели из этого массива, но фактически не удаляет `CObject` объекты.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Remarks

Если массив уже пуст, функция продолжает работать.

`RemoveAll`Функция освобождает всю память, используемую для хранения указателя.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::RemoveAll` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAll ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Пример

Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a>Кобаррай:: RemoveAt

Удаляет один или несколько элементов, начиная с указанного индекса в массиве.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

*нкаунт*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Remarks

В процессе он сдвигает все элементы над удаленными элементами. Он уменьшает верхнюю границу массива, но не освобождает память.

Если попытаться удалить больше элементов, чем содержится в массиве над точкой удаления, то отладочная версия библиотеки будет утверждена.

`RemoveAt`Функция удаляет `CObject` указатель из массива, но сам объект не удаляется.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::RemoveAt` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** *нкаунт* **= 1);**|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a>Кобаррай:: SetAt

Задает элемент массива по указанному индексу.

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0 и меньше или равен значению, возвращенному `GetUpperBound` .

*невелемент*<br/>
Указатель на объект, вставляемый в этот массив. Разрешено значение NULL.

### <a name="remarks"></a>Remarks

`SetAt`не приведет к увеличению размера массива. Используйте, `SetAtGrow` Если требуется, чтобы массив был автоматически расти.

Необходимо убедиться, что значение индекса соответствует допустимой позиции в массиве. Если он выходит за пределы допустимого диапазона, отладочная версия библиотеки утверждает.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::SetAt` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAt (INT_PTR** `nIndex` **, Byte** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, DWORD** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, uint** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, Word** `newElement` **);**|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a>Кобаррай:: Сетатгров

Задает элемент массива по указанному индексу.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Целочисленный индекс, который больше или равен 0.

*невелемент*<br/>
Указатель на объект, добавляемый в этот массив. Разрешено значение NULL.

### <a name="remarks"></a>Remarks

При необходимости массив автоматически растет (то есть верхняя граница корректируется для размещения нового элемента).

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::SetAtGrow` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void сетатгров (INT_PTR** `nIndex` **, Byte** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void сетатгров (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void сетатгров (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void сетатгров (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void сетатгров (INT_PTR** `nIndex` **, uint** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void сетатгров (INT_PTR** `nIndex` **, Word** `newElement` **);**<br /><br /> **Throw (CMemoryException \* );**|

### <a name="example"></a>Пример

  Список классов, используемых во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a>Кобаррай:: SetSize

Устанавливает размер пустого или существующего массива. При необходимости выделяет память.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*нневсизе*<br/>
Новый размер массива (число элементов). Должна быть не ниже 0.

*нгровби*<br/>
Минимальное число слотов элементов для выделения при необходимости увеличения размера.

### <a name="remarks"></a>Remarks

Если новый размер меньше старого, массив усекается и освобождается вся неиспользуемая память. Для повышения эффективности вызовите метод, `SetSize` чтобы задать размер массива перед его использованием. Это предотвращает необходимость перераспределения и копирования массива при каждом добавлении элемента.

Параметр *нгровби* влияет на выделение внутренней памяти во время роста массива. Его использование никогда не влияет на размер массива, сообщаемый `GetSize` и `GetUpperBound` .

Если размер массива увеличился, все вновь выделенные указатели **CObject** <strong>\*</strong> УСТАНАВЛИВАЮТСЯ в значение null.

В следующей таблице показаны другие функции элементов, аналогичные `CObArray::SetSize` .

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void setSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **Throw (CMemoryException \* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void setSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **Throw (CMemoryException \* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void setSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **Throw (CMemoryException \* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void setSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **Throw (CMemoryException \* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void setSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **Throw (CMemoryException \* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void setSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **=-1);**<br /><br /> **Throw (CMemoryException \* );**|

### <a name="example"></a>Пример

  См. пример для [кобаррай:: GetData](#getdata).

## <a name="see-also"></a>См. также раздел

[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кстрингаррай](../../mfc/reference/cstringarray-class.md)<br/>
[Класс Кптраррай](../../mfc/reference/cptrarray-class.md)<br/>
[Класс CByteArray](../../mfc/reference/cbytearray-class.md)<br/>
[Класс Квордаррай](../../mfc/reference/cwordarray-class.md)<br/>
[Класс Кдвордаррай](../../mfc/reference/cdwordarray-class.md)
