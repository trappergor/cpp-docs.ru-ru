---
title: Класс CObArray
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
ms.openlocfilehash: c19715f62704bfc97059421451929cbbec2506ce
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754476"
---
# <a name="cobarray-class"></a>Класс CObArray

Поддерживает массивы указателей `CObject` .

## <a name="syntax"></a>Синтаксис

```
class CObArray : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CObArray::CObArray](#cobarray)|Строит пустой массив `CObject` для указателей.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CObArray::Добавить](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[CObArray::Приложение](#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|
|[CObArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[Cobarray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CObArray::FreeExtra](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[Cobarray::GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CObArray::GetCount](#getcount)|Возвращает количество элементов в массиве.|
|[CObArray::GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[CObArray::GetSize](#getsize)|Возвращает количество элементов в массиве.|
|[CObArray::GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[Cobarray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CobArray::Isempty](#isempty)|Определяет, пуст ли массив.|
|[CObArray::RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[Cobarray::RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[Cobarray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[Cobarray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[CObArray::SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CObArray:оператор \[\]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Remarks

Эти массивы объектов похожи на массивы C, но они могут динамически сокращаться и расти по мере необходимости.

Индексы массива всегда начинаются с позиции 0. Вы можете решить, следует ли исправить верхнюю границу или разрешить расширению массива при добавлении элементов за текущей границой. Память распределяется смежно к верхней границе, даже если некоторые элементы являются недействительными.

В соответствии с Win32 размер объекта ограничен только доступной `CObArray` памятью.

Как и в блоке C, `CObArray` время доступа к индексированному элементу является постоянным и не зависит от размера массива.

`CObArray`включает IMPLEMENT_SERIAL макрос для поддержки сериализации и сброса его элементов. Если массив `CObject` указателей хранится в архиве, либо с перегруженным оператором `Serialize` вставки, либо с функцией члена, каждый `CObject` элемент, в свою очередь, сериализируется вместе с индексом массива.

Если вам нужна свалка отдельных `CObject` элементов в массиве, необходимо установить глубину `CDumpContext` объекта до 1 или больше.

Когда `CObArray` объект удаляется или когда его элементы `CObject` удаляются, удаляются только указатели, а не объекты, на которые они ссылаются.

> [!NOTE]
> Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Производство класса array аналогично производности списка. Подробнее о произветворении класса специальных списков [Collections](../../mfc/collections.md)см.

> [!NOTE]
> Если вы намереваетесь выполнить сериализацию массива, необходимо использовать IMPLEMENT_SERIAL макрос атакжем.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="cobarrayadd"></a><a name="add"></a>CObArray::Добавить

Добавляет новый элемент в конец массива, увеличив массив на 1.

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Параметры

*newElement*<br/>
Указатель, `CObject` который будет добавлен в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Remarks

Если [SetSize](#setsize) был использован с *nGrowBy* значение больше, чем 1, то дополнительная память может быть выделена. Однако верхняя граница увеличится только на 1.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::Add`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR Добавить (BYTE** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Добавить (DWORD);** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Добавить** <strong>\*</strong> `newElement` **(недействительным);**<br /><br /> **бросок (CMemoryException);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Добавить (LPCTSTR);** `newElement` **бросок (CMemoryException);\* **<br /><br /> **INT_PTR Добавить (конст CString** `newElement` **&);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Добавить (UINT);** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR Добавить** `newElement` **(WORD);**<br /><br /> **бросок (CMemoryException);\***|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Результаты этой программы следующие:

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

## <a name="cobarrayappend"></a><a name="append"></a>CObArray::Приложение

Вызовите эту функцию участника, чтобы добавить содержимое другого массива в конец данного массива.

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, которые будут приписано к массиву.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого придативного элемента.

### <a name="remarks"></a>Remarks

Массивы должны быть одного типа.

При необходимости `Append` можно выделить дополнительную память для размещения элементов, применяемых к массиву.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::Append`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR Приложение (конст CByteArray&** *src);* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR Append (const CDWordArray&** *src);* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR Приложение (const CPtrArray&** *src);* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR Приложение (конст CStringArray&** *src);* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR Приложение (const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR Приложение (Const CWordArray&** *src);* **);**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

## <a name="cobarraycopy"></a><a name="copy"></a>CObArray::Copy

Вызов ими функции участника, чтобы перезаписать элементы данного массива с элементами другого массива того же типа.

```cpp
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, которые будут скопированы в массив.

### <a name="remarks"></a>Remarks

`Copy`не освобождает память; однако, при `Copy` необходимости, может выделить дополнительную память для размещения элементов, скопированных на массив.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::Copy`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**пустота Копия (конст CByteArray&** *src);* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**пустота Копия (конст CDWordArray&** *src);* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**пустота Копия (конст CPtrArray&** *src);* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**пустота Копия (конст CStringArray&** *src);* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**аннулирование Копия (const CUIntArray&** *src);* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**пустота Копия (Конст CWordArray&** *src);* **);**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

## <a name="cobarraycobarray"></a><a name="cobarray"></a>CObArray::CObArray

Строит пустой `CObject` массив указателей.

```
CObArray();
```

### <a name="remarks"></a>Remarks

Массив растет один элемент за один раз.

В следующей таблице показаны другие `CObArray::CObArray`конструкторы, которые похожи на .

|Class|Конструктор|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**CByteArray();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

## <a name="cobarrayelementat"></a><a name="elementat"></a>Cobarray::ElementAt

Возвращает временную ссылку на указатель элемента в массиве.

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, который больше или равен 0 и меньше или равен `GetUpperBound`добавленному значению.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `CObject` указатель.

### <a name="remarks"></a>Remarks

Используется для реализации оператора левого назначения для массивов. Обратите внимание, что это расширенная функция, которая должна использоваться только для реализации операторов специальных массивов.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::ElementAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE& ElementAt** `nIndex` **(INT_PTR);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD& ElementAt** `nIndex` **(INT_PTR);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**\* пустота& Элементат (INT_PTR);** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Cstring& ElementAt** `nIndex` **(INT_PTR);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT& ElementAt** `nIndex` **(INT_PTR);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD& ElementAt(INT_PTR);** `nIndex` **);**|

### <a name="example"></a>Пример

  Смотрите пример [cObArray::GetSize](#getsize).

## <a name="cobarrayfreeextra"></a><a name="freeextra"></a>CObArray::FreeExtra

Освобождает любую дополнительную память, которая была выделена в то время как массив был выращен.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Remarks

Эта функция не влияет на размер или верхнюю границу массива.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::FreeExtra`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**пустота FreeExtra();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**пустота FreeExtra();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**пустота FreeExtra();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**пустота FreeExtra();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**пустота FreeExtra();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**пустота FreeExtra();**|

### <a name="example"></a>Пример

  Смотрите пример [CObArray::GetData](#getdata).

## <a name="cobarraygetat"></a><a name="getat"></a>Cobarray::GetAt

Возвращает элемент массива в указанном индексе.

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, который больше или равен 0 и меньше или равен `GetUpperBound`добавленному значению.

### <a name="return-value"></a>Возвращаемое значение

Элемент `CObject` указателя в настоящее время в этом индексе.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Прохождение отрицательного значения или значения, `GetUpperBound` превышающее возвращенное значение, приведет к неудавому утверждению.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::GetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**BYTE GetAt (INT_PTR)** `nIndex` **const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR)** `nIndex` **const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**\* пустота GetAt (INT_PTR)** `nIndex` **const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR)** `nIndex` **const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR)** `nIndex` **const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

## <a name="cobarraygetcount"></a><a name="getcount"></a>CObArray::GetCount

Возвращает количество элементов массива.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в массиве. Поскольку индексы на нулевом уровне, размер на 1 больше, чем самый большой индекс.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::GetCount`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount () const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount () const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount () const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount () const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount () const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

## <a name="cobarraygetdata"></a><a name="getdata"></a>CObArray::GetData

Используйте эту функцию члена, чтобы получить прямой доступ к элементам массива.

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив `CObject` указателей.

### <a name="remarks"></a>Remarks

Если элементы отсутствуют, `GetData` возвращаетнулнулнуло нулевую стоимость.

В то время как прямой доступ к элементам массива `GetData`может помочь вам работать быстрее, используйте осторожность при вызове; любые ошибки, которые вы делаете, непосредственно влияют на элементы вашего массива.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::GetData`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const BYTE\* GetData () Const; BYTE\* GetData ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData () const;DWORD\* GetData ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const\* \* пустота GetData ()\* \* Const;void GetData ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* GetData () Const; CString\* GetData ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* GetData () Const; UINT\* GetData ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const\* WORD GetData () Const; WORD\* GetData ();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

## <a name="cobarraygetsize"></a><a name="getsize"></a>CObArray::GetSize

Возвращает размер массива.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Remarks

Поскольку индексы на нулевом уровне, размер на 1 больше, чем самый большой индекс.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::GetSize`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize() Const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize() Const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize() Const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize() Const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize() Const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize() Const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

## <a name="cobarraygetupperbound"></a><a name="getupperbound"></a>CObArray::GetUpperBound

Возвращает текущую верхнюю границу этого массива.

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс верхней границы (нулевой).

### <a name="remarks"></a>Remarks

Поскольку индексы массива основаны на нулевом `GetSize`уровне, эта функция возвращает значение на 1 меньше, чем.

Условие `GetUpperBound( )` No -1 указывает на то, что массив не содержит элементов.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::GetUpperBound`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetUpperBound () Const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetUpperBound () Const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetUpperBound () Const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetUpperBound () Const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetUpperBound () Const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetUpperBound () Const;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

## <a name="cobarrayinsertat"></a><a name="insertat"></a>Cobarray::InsertAt

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

*Nindex*<br/>
Индекс, который может быть больше, чем `GetUpperBound`значение, возвращенное .

*newElement*<br/>
Указатель, `CObject` который будет помещен в этот массив. Допускается *новыйэлемент* стоимости NULL.

*Ncount*<br/>
Количество раз, когда этот элемент должен быть вставлен (по умолчанию до 1).

*nСтарт-индекс*<br/>
Индекс, который может быть больше, чем `GetUpperBound`значение, возвращенное .

*pNewArray*<br/>
Другой массив, содержащий элементы, которые будут добавлены в этот массив.

### <a name="remarks"></a>Remarks

Первая версия `InsertAt` вставки одного элемента (или нескольких копий элемента) в определенном индексе в массиве. В процессе он смещает вверх (путем приращения индекса) существующий элемент в этом индексе, и он перемещает вверх все элементы над ним.

Вторая версия вставляет все `CObArray` элементы из другой коллекции, начиная с позиции *nStartIndex.*

Функция, `SetAt` напротив, заменяет один указанный элемент массива и не сдвигает элементы.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::InsertAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**пустота InsertAt (INT_PTR,** `nIndex` **BYTE** `newElement` **, int** `nCount` No 1 **);**<br /><br /> **бросок (CMemoryException);\***<br /><br /> **пустота InsertAt (INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**пустота InsertAt (INT_PTR** `nIndex` **, DWORD** `newElement` **, Int** `nCount` **No 1 );**<br /><br /> **бросок (CMemoryException);\***<br /><br /> **пустота InsertAt (INT_PTR** `nStartIndex` **, CDWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**пустота InsertAt (INT_PTR,** `nIndex` **недействительным,** <strong>\*</strong> `newElement` **Int** `nCount` No 1 **);**<br /><br /> **бросок (CMemoryException);\***<br /><br /> **пустота InsertAt (INT_PTR** `nStartIndex` **, CPtrArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**пустота InsertAt (INT_PTR,** `nIndex` **LPCTSTR** `newElement` **, int** `nCount` No 1 **);**<br /><br /> **бросок (CMemoryException);\***<br /><br /> **пустота InsertAt (INT_PTR** `nStartIndex` **, CStringArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**пустота InsertAt(INT_PTR,** `nIndex` **UINT** `newElement` **, Int** `nCount` No 1 **);**<br /><br /> **бросок (CMemoryException);\***<br /><br /> **void InsertAt(INT_PTR** `nStartIndex` **, CUIntArray);** <strong>\*</strong> `pNewArray` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**пустота InsertAt (INT_PTR,** `nIndex` **WORD** `newElement` **, Int** `nCount` No 1 **);**<br /><br /> **бросок (CMemoryException);\***<br /><br /> **пустота InsertAt (INT_PTR** `nStartIndex` **, CWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **бросок (CMemoryException);\***|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Результаты этой программы следующие:

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

## <a name="cobarrayisempty"></a><a name="isempty"></a>CobArray::Isempty

Определяет, пуст ли массив.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если массив пуст; в противном случае 0.

## <a name="cobarrayoperator--"></a><a name="operator_at"></a>CObArray::оператор

Эти операторы подписных пословить являются удобной заменой и `SetAt` `GetAt` функций.

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Remarks

Первый оператор, вызванный для массивов, которые не являются **конст,** может быть использован либо справа (r-value) или слева (l-значение) оператора назначения. Второй, называемый **конст массивов,** может быть использован только справа.

Версия библиотеки Debug утверждает, что подтекст (или слева, либо справа от оператора назначения) выходит за рамки.

В следующей таблице показаны `CObArray::operator []`другие операторы, которые похожи на .

|Class|Оператор|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**ОПЕРАТОР& BYTE (int_ptr** `nindex` ** \);**<br /><br /> **ОПЕРАТОР BYTE (int_ptr** `nindex` ** \) конст;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Оператор& DWORD (int_ptr** `nindex` ** \);**<br /><br /> **Оператор DWORD (int_ptr** `nindex` ** \) конст;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**недействительный\* оператор& (int_ptr** `nindex` ** \);**<br /><br /> **пустота\* оператора (int_ptr** `nindex` ** \) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Оператор cString& (int_ptr** `nindex` ** \);**<br /><br /> **Оператор CString (int_ptr** `nindex` ** \) конст;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Оператор UINT& (int_ptr** `nindex` ** \);**<br /><br /> **Оператор UINT (int_ptr** `nindex` ** \) конст;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**&-оператор WORD (int_ptr** `nindex` ** \);**<br /><br /> **ОПЕРАТОР WORD (int_ptr** `nindex` ** \) конст;**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

## <a name="cobarrayremoveall"></a><a name="removeall"></a>CObArray::RemoveAll

Удаляет все указатели из этого массива, `CObject` но на самом деле не удаляет объекты.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Remarks

Если массив уже пуст, функция по-прежнему работает.

Функция `RemoveAll` освобождает всю память, используемую для хранения указателей.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::RemoveAll`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**пустота RemoveAll();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**пустота RemoveAll();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**пустота RemoveAll();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**пустота RemoveAll();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**пустота RemoveAll();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**пустота RemoveAll();**|

### <a name="example"></a>Пример

Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

## <a name="cobarrayremoveat"></a><a name="removeat"></a>Cobarray::RemoveAt

Удаляет один или несколько элементов, начиная с заданного индекса в массиве.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, который больше или равен 0 и меньше или равен `GetUpperBound`добавленному значению.

*Ncount*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Remarks

В процессе он смещает вниз все элементы выше удаленного элемента (ы). Он присваивает верхнюю границу массива, но не освобождает память.

Если вы попытаетесь удалить больше элементов, чем содержится в массиве над точкой удаления, то версия библиотеки Debug утверждает.

Функция `RemoveAt` удаляет указатель `CObject` из массива, но не удаляет сам объект.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::RemoveAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt(INT_PTR,** `nIndex` **INT_PTR** `nCount` **No 1 );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt(INT_PTR,** `nIndex` **INT_PTR** `nCount` **No 1 );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt(INT_PTR,** `nIndex` **INT_PTR** `nCount` **No 1 );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt(INT_PTR,** `nIndex` **INT_PTR** `nCount` **No 1 );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt(INT_PTR,** `nIndex` **INT_PTR** `nCount` **No 1 );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt (INT_PTR,** `nIndex` **INT_PTR** *nCount* No 1 **);**|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Результаты этой программы следующие:

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

## <a name="cobarraysetat"></a><a name="setat"></a>Cobarray::SetAt

Устанавливает элемент массива в указанном индексе.

```cpp
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Индекс, который больше или равен 0 и меньше или равен `GetUpperBound`добавленному значению.

*newElement*<br/>
Указатель объекта, который будет вставлен в этот массив. Допускается значение NULL.

### <a name="remarks"></a>Remarks

`SetAt`не приведет к росту массива. Используйте, `SetAtGrow` если вы хотите, чтобы массив рос автоматически.

Необходимо убедиться, что значение индекса представляет собой допустимое положение в массиве. Если это выходит за рамки, то версия библиотеки Debug утверждает.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::SetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**пустота SetAt (INT_PTR,** `nIndex` **BYTE);** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**пустота SetAt (INT_PTR** `nIndex` **, DWORD);** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**пустота SetAt (INT_PTR,** `nIndex` **недействительным);** **, void** <strong>\*</strong> `newElement`|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**апотизм SetAt (INT_PTR** `nIndex` **, LPCTSTR);** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**недействительным SetAt (INT_PTR** `nIndex` **, UINT);** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**пустота SetAt (INT_PTR,** `nIndex` **WORD);** **, WORD** `newElement`|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Результаты этой программы следующие:

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

## <a name="cobarraysetatgrow"></a><a name="setatgrow"></a>Cobarray::SetAtGrow

Устанавливает элемент массива в указанном индексе.

```cpp
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Равный индекс, который больше или равен 0.

*newElement*<br/>
Указатель объекта, который будет добавлен в этот массив. Допускается значение NULL.

### <a name="remarks"></a>Remarks

Массив растет автоматически, если это необходимо (т.е. верхняя граница регулируется с учетом нового элемента).

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::SetAtGrow`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow (INT_PTR,** `nIndex` **BYTE);** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**недействительным SetAtGrow (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**недействительным SetAtGrow (INT_PTR,** `nIndex` <strong>\*</strong> `newElement` **недействительным);** **, void**<br /><br /> **бросок (CMemoryException);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**недействительным SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, UINT);** `newElement` **);**<br /><br /> **бросок (CMemoryException);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` , **WORD);** **, WORD** `newElement`<br /><br /> **бросок (CMemoryException);\***|

### <a name="example"></a>Пример

  Смотрите [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) для перечисления класса, используемого `CAge` во всех примерах коллекций.

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Результаты этой программы следующие:

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

## <a name="cobarraysetsize"></a><a name="setsize"></a>CObArray::SetSize

Устанавливает размер пустого или существующего массива; распределяет память при необходимости.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*nNewSize*<br/>
Новый размер массива (количество элементов). Должно быть больше или равно 0.

*nGrowBy*<br/>
Минимальное количество слотов элементов, чтобы выделить, если увеличение размера необходимо.

### <a name="remarks"></a>Remarks

Если новый размер меньше старого, то массив усечен и все неиспользованные памяти освобождены. Для повышения `SetSize` эффективности позвоните, чтобы установить размер массива перед его использованием. Это предотвращает необходимость перераспределить и скопировать массив каждый раз при добавлении элемента.

Параметр *nGrowBy* влияет на внутреннее распределение памяти, пока массив растет. Его использование никогда не влияет `GetSize` на `GetUpperBound`размер массива, как сообщается и .

Если размер массива вырос, все недавно выделенные указатели **CObject** <strong>\*</strong> установлены в NULL.

В следующей таблице показаны другие функции участника, которые аналогичны `CObArray::SetSize`.

|Class|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**пустота SetSize (INT_PTR,** `nNewSize` **int** `nGrowBy` **-1 );**<br /><br /> **бросок (CMemoryException);\***|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**пустота SetSize (INT_PTR,** `nNewSize` **int** `nGrowBy` **-1 );**<br /><br /> **бросок (CMemoryException);\***|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**пустота SetSize (INT_PTR,** `nNewSize` **int** `nGrowBy` **-1 );**<br /><br /> **бросок (CMemoryException);\***|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**пустота SetSize (INT_PTR,** `nNewSize` **int** `nGrowBy` **-1 );**<br /><br /> **бросок (CMemoryException);\***|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**пустота SetSize (INT_PTR,** `nNewSize` **int** `nGrowBy` **-1 );**<br /><br /> **бросок (CMemoryException);\***|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**пустота SetSize (INT_PTR,** `nNewSize` **int** `nGrowBy` **-1 );**<br /><br /> **бросок (CMemoryException);\***|

### <a name="example"></a>Пример

  Смотрите пример [CObArray::GetData](#getdata).

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStringArray](../../mfc/reference/cstringarray-class.md)<br/>
[Класс CPtrArray](../../mfc/reference/cptrarray-class.md)<br/>
[Класс CByteArray](../../mfc/reference/cbytearray-class.md)<br/>
[Класс CWordArray](../../mfc/reference/cwordarray-class.md)<br/>
[Класс CDWordArray](../../mfc/reference/cdwordarray-class.md)
