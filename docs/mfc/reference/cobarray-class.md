---
title: Класс CObArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b71904fb20348985dee78e5dd06e0e3c60797782
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067973"
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
|[CObArray::CObArray](#cobarray)|Создает пустой массив для `CObject` указатели.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CObArray::Add](#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[CObArray::Append](#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|
|[CObArray::Copy](#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[CObArray::ElementAt](#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[CObArray::FreeExtra](#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[CObArray::GetAt](#getat)|Возвращает значение по указанному индексу.|
|[CObArray::GetCount](#getcount)|Возвращает количество элементов в массиве.|
|[CObArray::GetData](#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[CObArray::GetSize](#getsize)|Возвращает количество элементов в массиве.|
|[CObArray::GetUpperBound](#getupperbound)|Возвращает самый большой допустимый индекс.|
|[CObArray::InsertAt](#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[CObArray::IsEmpty](#isempty)|Определяет, пуст ли массив.|
|[CObArray::RemoveAll](#removeall)|Удаляет все элементы из этого массива.|
|[CObArray::RemoveAt](#removeat)|Удаляет элемент по указанному индексу.|
|[CObArray::SetAt](#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[CObArray::SetAtGrow](#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[CObArray::SetSize](#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[[CObArray::operator]](#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Примечания

Эти массивы объектов похожи на массивы C, но они могут динамически сжать и увеличиваться при необходимости.

Индексы массива всегда начинаются с позиции 0. Можно ли исправить верхнюю границу или разрешить массива развернуть при добавлении элементов после текущей границей. Память выделяется непрерывно верхней границей, даже если некоторые элементы имеют значение null.

В разделе Win32, размер `CObArray` объекта ограничено только доступной памяти.

Как и в массиве C время обращения к `CObArray` индексированный элемент является константой и не зависит от размера массива.

`CObArray` включает в себя IMPLEMENT_SERIAL-макрос для поддержки сериализации и записи элементов в дамп. Если массив `CObject` указатели хранится в архив с помощью перегруженного оператора вставки или `Serialize` функция-член, чтобы каждый `CObject` элемент в свою очередь, сериализуется вместе с его индекса массива.

Если вам требуется дамп отдельных `CObject` элементов в массиве, необходимо задать глубину `CDumpContext` , который больше или равно 1.

Когда `CObArray` объект удаляется или когда его элементы удаляются, только `CObject` будут удалены указатели, не объекты, они ссылаются.

> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Для создания производного класса массива похож на список наследования. Дополнительные сведения о производный класс списка специального назначения, см. в статье [коллекций](../../mfc/collections.md).

> [!NOTE]
>  IMPLEMENT_SERIAL-макрос необходимо использовать в реализации в производном классе, если вы собираетесь сериализации массива.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObArray`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

##  <a name="add"></a>  CObArray::Add

Добавляет новый элемент в конец массива, увеличение массива на 1.

```
INT_PTR Add(CObject* newElement);
```

### <a name="parameters"></a>Параметры

*newElement*<br/>
`CObject` Указатель для добавления в этот массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс добавленного элемента.

### <a name="remarks"></a>Примечания

Если [SetSize](#setsize) оно использовалось с *nGrowBy* значение больше 1, то дополнительная память может выделяться. Тем не менее верхнюю границу, будут увеличены только 1.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::Add`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Добавление INT_PTR (BYTE** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Добавление INT_PTR (DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Добавление INT_PTR (void** <strong>\*</strong> `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Добавление INT_PTR (LPCTSTR** `newElement` **); throw (CMemoryException\* );**<br /><br /> **INT_PTR Add(const CString&** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Добавление INT_PTR (целое число без знака** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Добавление INT_PTR (WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]

Далее приведены результаты из этой программы.

```Output
Add example: A CObArray with 2 elements
[0] = a CAge at $442A 21
[1] = a CAge at $4468 40
```

##  <a name="append"></a>  CObArray::Append

Вызывайте эту функцию элемента для добавления содержимого другого массива в конец заданного массива.

```
INT_PTR Append(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов для добавления в массив.

### <a name="return-value"></a>Возвращаемое значение

Индекс первый добавленный элемент.

### <a name="remarks"></a>Примечания

Массивы должны иметь тот же тип.

При необходимости `Append` может выделить дополнительный объем памяти для размещения элементов, добавляемый в конец массива.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::Append`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Добавление INT_PTR (const CByteArray &** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Добавление INT_PTR (const CDWordArray &** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Добавление INT_PTR (const CPtrArray &** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Добавление INT_PTR (const CStringArray &** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Добавление INT_PTR (const CUIntArray &** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Добавление INT_PTR (const CWordArray &** *src* **);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]

##  <a name="copy"></a>  CObArray::Copy

Вызовите эту функцию-член для перезаписи элементы заданного массива с элементами другого массива того же типа.

```
void Copy(const CObArray& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Источник элементов, копируемых в массив.

### <a name="remarks"></a>Примечания

`Copy` не освобождает память; Тем не менее, при необходимости `Copy` может выделить дополнительный объем памяти для размещения элементов, копируемых в массив.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::Copy`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void копия (const CByteArray &** *src* **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void копия (const CDWordArray &** *src* **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void копия (const CPtrArray &** *src* **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void копия (const CStringArray &** *src* **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void копия (const CUIntArray &** *src* **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void копия (const CWordArray &** *src* **);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]

##  <a name="cobarray"></a>  CObArray::CObArray

Создает пустой `CObject` массив указателей.

```
CObArray();
```

### <a name="remarks"></a>Примечания

Массив растет одного элемента за раз.

В следующей таблице приведены другие конструкторы, которые похожи на `CObArray::CObArray`.

|Класс|Конструктор|
|-----------|-----------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**(CByteArray);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**(CDWordArray);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**(CPtrArray);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**(CStringArray);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**(CUIntArray);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**(CWordArray);**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]

##  <a name="elementat"></a>  CObArray::ElementAt

Возвращает временную ссылку на указатель элемента в массиве.

```
CObject*& ElementAt(INT_PTR nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `GetUpperBound`.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на `CObject` указатель.

### <a name="remarks"></a>Примечания

Он используется для реализации оператор слева от оператора присваивания для массивов. Обратите внимание, что это расширенную функцию, который должен использоваться только для реализации специальных массива операторы.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::ElementAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Смещение в ба & ElementAt (INT_PTR** `nIndex` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & ElementAt (INT_PTR** `nIndex` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& ElementAt (INT_PTR** `nIndex` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & ElementAt (INT_PTR** `nIndex` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Целое число без знака & ElementAt (INT_PTR** `nIndex` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & ElementAt (INT_PTR** `nIndex` **);**|

### <a name="example"></a>Пример

  См. в примере [CObArray::GetSize](#getsize).

##  <a name="freeextra"></a>  CObArray::FreeExtra

Освобождает любой дополнительной памяти, который был выделен хотя при явном массива.

```
void FreeExtra();
```

### <a name="remarks"></a>Примечания

Эта функция не влияет на размер или верхней границы массива.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::FreeExtra`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void (FreeExtra);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void (FreeExtra);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void (FreeExtra);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void (FreeExtra);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void (FreeExtra);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void (FreeExtra);**|

### <a name="example"></a>Пример

  См. в примере [CObArray::GetData](#getdata).

##  <a name="getat"></a>  CObArray::GetAt

Возвращает элемент массива по указанному индексу.

```
CObject* GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `GetUpperBound`.

### <a name="return-value"></a>Возвращаемое значение

`CObject` Указатель на элемент в настоящее время на этот индекс.

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Передача отрицательное значение или значение больше, чем значение, возвращенное `GetUpperBound` приведет к утверждение, вызвавшее сбой.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::GetAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**GetAt БАЙТОВ (INT_PTR** `nIndex` **) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\* GetAt (INT_PTR** `nIndex` **) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Целое число без знака GetAt (INT_PTR** `nIndex` **) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]

##  <a name="getcount"></a>  CObArray::GetCount

Возвращает количество элементов массива.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в массиве.

### <a name="remarks"></a>Примечания

Вызовите этот метод для получения числа элементов в массиве. Так как индексы отсчитываются от нуля, размер равен 1, больше, чем наибольший индекс.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::GetCount`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**(Const; INT_PTR GetCount)**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**(Const; INT_PTR GetCount)**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**(Const; INT_PTR GetCount)**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**(Const; INT_PTR GetCount)**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**(Const; INT_PTR GetCount)**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**(Const; INT_PTR GetCount)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]

##  <a name="getdata"></a>  CObArray::GetData

Используйте эту функцию-член для прямого доступа к элементам в массиве.

```
const CObject** GetData() const;

CObject** GetData();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на массив `CObject` указатели.

### <a name="remarks"></a>Примечания

Если нет элементов, `GetData` возвращает значение null.

Хотя прямой доступ к элементам массива может помочь вам работать быстрее, будьте осторожны при вызове `GetData`; все ошибки, вносимые непосредственно влияют на элементы массива.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::GetData`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**const БАЙТОВ\* () GetData const; БАЙТОВ\* GetData ();**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData const (); DWORD\* GetData ();**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const void\* \* (GetData) const; void\* \* GetData ();**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* () GetData const; CString\* GetData ();**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**целое число без знака const\* () GetData const; Целое число без знака\* GetData ();**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD\* () GetData const; WORD\* GetData ();**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]

##  <a name="getsize"></a>  CObArray::GetSize

Возвращает размер массива.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Примечания

Так как индексы отсчитываются от нуля, размер равен 1, больше, чем наибольший индекс.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::GetSize`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**(Const; INT_PTR GetSize)**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**(Const; INT_PTR GetSize)**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**(Const; INT_PTR GetSize)**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**(Const; INT_PTR GetSize)**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**(Const; INT_PTR GetSize)**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**(Const; INT_PTR GetSize)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]

##  <a name="getupperbound"></a>  CObArray::GetUpperBound

Возвращает текущий верхнюю границу массива.

```
INT_PTR GetUpperBound() const;
```

### <a name="return-value"></a>Возвращаемое значение

Индекс (отсчитываемый от нуля) верхнюю границу.

### <a name="remarks"></a>Примечания

Так как массив индексы отсчитываются от нуля, эта функция возвращает значение 1 меньше, чем `GetSize`.

Условие `GetUpperBound( )` = -1 показывает, что массив не содержит элементов.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::GetUpperBound`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**(Const; INT_PTR GetUpperBound)**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**(Const; INT_PTR GetUpperBound)**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**(Const; INT_PTR GetUpperBound)**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**(Const; INT_PTR GetUpperBound)**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**(Const; INT_PTR GetUpperBound)**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**(Const; INT_PTR GetUpperBound)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]

##  <a name="insertat"></a>  CObArray::InsertAt

Вставляет элемент (или все элементы в другом массиве) по указанному индексу.

```
void InsertAt(
    INT_PTR nIndex,
    CObject* newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CObArray* pNewArray);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который может быть больше, чем значение, возвращенное `GetUpperBound`.

*newElement*<br/>
`CObject` Указатель помещается в этот массив. Объект *newElement* значения разрешено значение NULL.

*nCount*<br/>
Количество раз, когда этот элемент должен быть вставлен (по умолчанию — 1).

*nStartIndex*<br/>
Целочисленный индекс, который может быть больше, чем значение, возвращенное `GetUpperBound`.

*pNewArray*<br/>
Другой массив, содержащий элементы для добавления в этот массив.

### <a name="remarks"></a>Примечания

Первая версия `InsertAt` вставляет один элемент (или несколько копий элемента) с указанным индексом в массиве. В процессе, он передвигается (путем увеличения индекс) существующий элемент в этот индекс и его смещает все элементы над ним.

Вторая версия вставляет все элементы из другого `CObArray` коллекции, начиная с *nStartIndex* позиции.

`SetAt` Функции, напротив, заменяет один указанный элемент массива и не переместится какие-либо элементы.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::InsertAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, БАЙТОВ** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CByteArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CDWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CPtrArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CStringArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, целое число без знака** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CUIntArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CWordArray** <strong>\*</strong> `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]

Далее приведены результаты из этой программы.

```Output
InsertAt example: A CObArray with 3 elements
[0] = a CAge at $45C8 21
[1] = a CAge at $4646 30
[2] = a CAge at $4606 40
```

##  <a name="isempty"></a>  CObArray::IsEmpty

Определяет, пуст ли массив.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если массив пуст; в противном случае 0.

##  <a name="operator_at"></a>  [CObArray::operator]

Эти подстрочного оператора являются удобным заменой `SetAt` и `GetAt` функции.

```
CObject*& operator[](int_ptr nindex);
CObject* operator[](int_ptr nindex) const;
```

### <a name="remarks"></a>Примечания

Первый оператор, вызывается для массивов, которые не являются **const**, может быть использована для (r-значение) справа или слева от оператора присваивания (l значение). Второй, вызывается для **const** массивы, может использоваться только в правой части.

Отладочная версия библиотеки утверждает, если индекс (либо слева или справа от оператора присваивания) выходит за границы.

В следующей таблице приведены другие операторы, которые похожи на `CObArray::operator []`.

|Класс|Оператор|
|-----------|--------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**Оператор & BYTE [] (int_ptr** `nindex`  **\);**<br /><br /> **Operator BYTE [] (int_ptr** `nindex`  **\) const;**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & -оператор [] (int_ptr** `nindex`  **\);**<br /><br /> **Оператор [] DWORD (int_ptr** `nindex`  **\) const;**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& operator [] (int_ptr** `nindex`  **\);**<br /><br /> **void\* operator [] (int_ptr** `nindex`  **\) const;**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & -оператор [] (int_ptr** `nindex`  **\);**<br /><br /> **CString operator [] (int_ptr** `nindex`  **\) const;**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Целое число без знака & -оператор [] (int_ptr** `nindex`  **\);**<br /><br /> **Оператор [] целое число без знака (int_ptr** `nindex`  **\) const;**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & -оператор [] (int_ptr** `nindex`  **\);**<br /><br /> **СЛОВО operator [] (int_ptr** `nindex`  **\) const;**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]

##  <a name="removeall"></a>  CObArray::RemoveAll

Удаляет все указатели из этого массива, но фактически не удаляются `CObject` объектов.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Если массив уже является пустым, функция по-прежнему работает.

`RemoveAll` Функция освобождает всю память, используемая для хранения указателя.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::RemoveAll`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void (RemoveAll);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void (RemoveAll);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void (RemoveAll);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void (RemoveAll);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void (RemoveAll);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void (RemoveAll);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]

##  <a name="removeat"></a>  CObArray::RemoveAt

Удаляет один или несколько элементов, начиная с указанного индекса в массиве.

```
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `GetUpperBound`.

*nCount*<br/>
Число удаляемых элементов.

### <a name="remarks"></a>Примечания

В процессе сдвигаются вниз всех элементов, расположенных выше удаленных элементов. Он уменьшает верхняя граница массива, но не освобождает память.

Если вы попытаетесь удалить больше элементов, чем содержащиеся в массиве выше точки удаления, утверждает отладочной версии библиотеки.

`RemoveAt` Функция удаляет `CObject` указатель из массива, но не приводит к удалению самого объекта.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::RemoveAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1);**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]

Далее приведены результаты из этой программы.

```Output
RemoveAt example: A CObArray with 1 elements
[0] = a CAge at $4606 40
```

##  <a name="setat"></a>  CObArray::SetAt

Задает элемент массива по указанному индексу.

```
void SetAt(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0 и меньше или равно значение, возвращенное `GetUpperBound`.

*newElement*<br/>
Указатель на объект, который необходимо вставить в этот массив. Допускается значение NULL.

### <a name="remarks"></a>Примечания

`SetAt` не вызовет массива расти. Используйте `SetAtGrow` Если автоматическое увеличение массива.

Необходимо убедиться, что значение индекса представляет допустимую позицию в массиве. Если он выходит за границы, утверждает отладочной версии библиотеки.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::SetAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAt (INT_PTR** `nIndex` **, БАЙТОВ** `newElement` **);**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, DWORD** `newElement` **);**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, целое число без знака** `newElement` **);**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, WORD** `newElement` **);**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]

Далее приведены результаты из этой программы.

```Output
SetAt example: A CObArray with 2 elements
[0] = a CAge at $47E0 30
[1] = a CAge at $47A0 40
```

##  <a name="setatgrow"></a>  CObArray::SetAtGrow

Задает элемент массива по указанному индексу.

```
void SetAtGrow(
    INT_PTR nIndex,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Целочисленный индекс, который больше или равно 0.

*newElement*<br/>
Указатель на объект, добавляемый в этот массив. Допускается значение NULL.

### <a name="remarks"></a>Примечания

Массив увеличивается автоматически при необходимости (то есть верхнюю границу корректируется для размещения нового элемента).

В следующей таблице показаны другой член функции, которые похожи на `CObArray::SetAtGrow`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, БАЙТОВ** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, void** <strong>\*</strong> `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, целое число без знака** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]

Далее приведены результаты из этой программы.

```Output
SetAtGrow example: A CObArray with 4 elements
[0] = a CAge at $47C0 21
[1] = a CAge at $4800 40
[2] = NULL
[3] = a CAge at $4840 65
```

##  <a name="setsize"></a>  CObArray::SetSize

Устанавливает размер массива пустой или существующий; Выделяет память при необходимости.

```
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Параметры

*nNewSize*<br/>
Новый размер массива (число элементов). Должно быть больше или равно 0.

*nGrowBy*<br/>
Минимальное число слотов элемент для выделения, если увеличение размера не требуется.

### <a name="remarks"></a>Примечания

Если новый размер меньше, чем старого, массив усекается, а всю неиспользуемую память освобождается. Для повышения эффективности, вызовите `SetSize` для задания размера массива перед его использованием. Это устраняет необходимость повторного выделения и копирования каждый раз при добавлении элемента массива.

*NGrowBy* параметр влияет на внутренней памяти, хотя массива увеличивается. Его использование не влияет на размер массива, предоставленное `GetSize` и `GetUpperBound`.

Если размер массива стал, все новые выделенных **CObject** <strong>\*</strong> указатели, присваивается значение NULL.

В следующей таблице показаны другой член функции, которые похожи на `CObArray::SetSize`.

|Класс|Функция-член|
|-----------|---------------------|
|[CByteArray](../../mfc/reference/cbytearray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|

### <a name="example"></a>Пример

  См. в примере [CObArray::GetData](#getdata).

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStringArray](../../mfc/reference/cstringarray-class.md)<br/>
[Класс CPtrArray](../../mfc/reference/cptrarray-class.md)<br/>
[Класс CByteArray](../../mfc/reference/cbytearray-class.md)<br/>
[Класс CWordArray](../../mfc/reference/cwordarray-class.md)<br/>
[Класс CDWordArray](../../mfc/reference/cdwordarray-class.md)
