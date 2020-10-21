---
title: Класс Коблист
ms.date: 11/04/2016
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
ms.openlocfilehash: a13363ef9b200051c26781ab6e9870a10de06d88
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274590"
---
# <a name="coblist-class"></a>Класс Коблист

Поддерживает упорядоченные списки неуникальных `CObject` указателей, доступных последовательно или по значению указателя.

## <a name="syntax"></a>Синтаксис

```
class CObList : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Коблист:: Коблист](#coblist)|Конструирует пустой список для `CObject` указателей.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Коблист:: Аддхеад](#addhead)|Добавляет элемент (или все элементы из другого списка) в заголовок списка (создает новый заголовок).|
|[Коблист:: AddTail](#addtail)|Добавляет элемент (или все элементы из другого списка) в конец списка (создает новый хвост).|
|[Коблист:: Find](#find)|Возвращает расположение элемента, заданного значением указателя.|
|[Коблист:: FindIndex](#findindex)|Возвращает расположение элемента, указанного с помощью индекса, начинающегося с нуля.|
|[Коблист:: GetAt](#getat)|Возвращает элемент в заданной позиции.|
|[Коблист:: NOCOUNT](#getcount)|Возвращает число элементов в этом списке.|
|[Коблист:: onhead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[Коблист:: Жесеадпоситион](#getheadposition)|Возвращает расположение головного элемента списка.|
|[Коблист:: GetNext](#getnext)|Возвращает следующий элемент для итерации.|
|[Коблист:: prev](#getprev)|Возвращает предыдущий элемент для итерации.|
|[Коблист:: DataSize](#getsize)|Возвращает число элементов в этом списке.|
|[Коблист:: tail](#gettail)|Возвращает заключительный элемент списка (не может быть пустым).|
|[Коблист:: Жеттаилпоситион](#gettailposition)|Возвращает расположение элемента хвоста в списке.|
|[Коблист:: InsertAfter](#insertafter)|Вставляет новый элемент после заданной позицией.|
|[Коблист:: методов insertBefore](#insertbefore)|Вставляет новый элемент перед заданной позицией.|
|[Коблист:: IsEmpty](#isempty)|Проверяет условие пустого списка (нет элементов).|
|[Коблист:: RemoveAll](#removeall)|Удаляет все элементы из этого списка.|
|[Коблист:: RemoveAt](#removeat)|Удаляет элемент из этого списка, заданный по положению.|
|[Коблист:: Ремовехеад](#removehead)|Удаляет элемент из заголовка списка.|
|[Коблист:: Ремоветаил](#removetail)|Удаляет элемент из хвоста списка.|
|[Коблист:: SetAt](#setat)|Задает элемент в заданной позиции.|

## <a name="remarks"></a>Remarks

`CObList` списки ведут себя как двунаправленные списки.

Переменная типа "расположение" является ключом для списка. Можно использовать переменную позиции как итератор для последовательного прохода по списку и как закладку для размещения. Однако позиция не совпадает с индексом.

Вставка элемента происходит очень быстро в заголовке списка, в хвосте и в известной позиции. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может выполняться медленно, если список длинный.

`CObList` включает макрос IMPLEMENT_SERIAL для поддержки сериализации и дампа его элементов. Если список `CObject` указателей хранится в архиве либо с перегруженным оператором вставки, либо с `Serialize` функцией-членом, каждый `CObject` элемент сериализуется в свою очередь.

Если вам нужен дамп отдельных `CObject` элементов в списке, необходимо задать для контекста дампа значение 1 или больше.

При `CObList` удалении объекта или удалении его элементов `CObject` удаляются только указатели, а не объекты, на которые они ссылаются.

Вы можете создавать собственные классы из `CObList` . Новый класс списка, предназначенный для хранения указателей на объекты, производные от `CObject` , добавляет новые элементы данных и новые функции элементов. Обратите внимание, что результирующий список не строго типизирован, так как он допускает вставку `CObject` указателя.

> [!NOTE]
> Если предполагается сериализовать список, необходимо использовать макрос [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) в реализации производного класса.

Дополнительные сведения об использовании `CObList` см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Requirements (Требования)

**Заголовок:** афксколл. h

## <a name="coblistaddhead"></a><a name="addhead"></a> Коблист:: Аддхеад

Добавляет новый элемент или список элементов в заголовок этого списка.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*невелемент*<br/>
`CObject`Указатель, добавляемый в этот список.

*пневлист*<br/>
Указатель на другой `CObList` список. Элементы в *пневлист* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение расположения вновь вставленного элемента.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::AddHead` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Аддхеад позиций (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void аддхеад (кптрлист** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Расположение аддхеад (const CString&** `newElement` **);**<br /><br /> **Расположение аддхеад (LPCTSTR** `newElement` **);**<br /><br /> **void аддхеад (кстринглист** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Remarks

Перед операцией список может быть пустым.

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a> Коблист:: AddTail

Добавляет новый элемент или список элементов в конец этого списка.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*невелемент*<br/>
`CObject`Указатель, добавляемый в этот список.

*пневлист*<br/>
Указатель на другой `CObList` список. Элементы в *пневлист* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение расположения вновь вставленного элемента.

### <a name="remarks"></a>Remarks

Перед операцией список может быть пустым.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::AddTail` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**AddTail позиций (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (кптрлист** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Расположение AddTail (const CString&** `newElement` **);**<br /><br /> **Расположение AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (кстринглист** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a> Коблист:: Коблист

Конструирует пустой `CObject` список указателей.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*нблокксизе*<br/>
Гранулярность выделения памяти для расширения списка.

### <a name="remarks"></a>Remarks

По мере роста списка память выделяется в единицах *нблокксизе* записей. При сбое выделения памяти `CMemoryException` создается исключение.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::CObList` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Кптрлист (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Кстринглист (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Пример

  Ниже приведен список `CObject` классов, производных от, `CAge` используемых во всех примерах коллекции:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Ниже приведен пример `CObList` использования конструктора.

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a> Коблист:: Find

Выполняет поиск в списке последовательно, чтобы найти первый `CObject` указатель, соответствующий указанному `CObject` указателю.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Параметры

*сеарчвалуе*<br/>
Указатель объекта, который должен быть найден в этом списке.

*стартафтер*<br/>
Начальное расположение для поиска.

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если объект не найден.

### <a name="remarks"></a>Remarks

Обратите внимание, что сравниваются значения указателя, а не содержимое объектов.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::Find` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Поиск по положению (void** <strong>\*</strong> `searchValue` **, Расположение** `startAfter` **= Null) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Поиск по положению (LPCTSTR** `searchValue` **, положением** `startAfter` **= null) const;**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a> Коблист:: FindIndex

Использует значение *ниндекс* в качестве индекса в списке.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*ниндекс*<br/>
Отсчитываемый от нуля индекс элемента списка, который необходимо найти.

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если *ниндекс* слишком большой. (Платформа создает утверждение, если *ниндекс* является отрицательным.)

### <a name="remarks"></a>Remarks

Он запускает последовательное сканирование из заголовка списка, останавливаясь на *n*-ом элементе.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::FindIndex` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**FindIndex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a> Коблист:: GetAt

Переменная типа "расположение" является ключом для списка.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*position*<br/>
Значение расположения, возвращаемое предыдущим `GetHeadPosition` `Find` вызовом функции-члена или.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

Это не то же самое, что и индекс, и вы не можете самостоятельно обрабатывать значение позиции. `GetAt` Извлекает `CObject` указатель, связанный с заданной позицией.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& GetAt (положением расположения** *position* **) const;**<br /><br /> **void \*& GetAt (расположение расположения** *position* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetAt (** *положением* расположения **) const;**<br /><br /> **CString& GetAt (** *Расположение* расположения **);**|

### <a name="example"></a>Пример

  См. пример для [FindIndex](#findindex).

## <a name="coblistgetcount"></a><a name="getcount"></a> Коблист:: NOCOUNT

Возвращает число элементов в этом списке.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение, содержащее число элементов.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetCount` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR вычислить const ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR вычислить const ();**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a> Коблист:: onhead

Возвращает `CObject` указатель, представляющий головной элемент этого списка.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если доступ к списку осуществляется через указатель на `const CObList` , `GetHead` возвращается `CObject` указатель. Это позволяет использовать функцию только с правой стороны оператора присваивания и тем самым защищает список от изменения.

Если доступ к списку осуществляется напрямую или через указатель на `CObList` , `GetHead` возвращается ссылка на `CObject` указатель. Это позволяет использовать функцию с любой стороны оператора присваивания и тем самым допустить изменение записей в списке.

### <a name="remarks"></a>Remarks

Перед вызовом необходимо убедиться, что список не пуст `GetHead` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetHead` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*&-Head () const; void \*&-Head ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString&-Head () const; CString&-Head ();**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

В следующем примере показано использование `GetHead` в левой части оператора присваивания.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a> Коблист:: Жесеадпоситион

Возвращает расположение головного элемента этого списка.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetHeadPosition` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Жесеадпоситион () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Жесеадпоситион () const;**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a> Коблист:: GetNext

Возвращает элемент List, определенный параметром *rPosition*, а затем задает для *rPosition* `POSITION` значение следующей записи в списке.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение значения value, возвращаемое предыдущим `GetNext` , `GetHeadPosition` или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

Можно использовать `GetNext` в цикле прямой итерации, если исходное расположение устанавливается с вызовом `GetHeadPosition` или `Find` .

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если извлеченный элемент является последним в списке, новое значение *rPosition* устанавливается в NULL.

Элемент можно удалить во время итерации. См. пример для [RemoveAt](#removeat).

> [!NOTE]
> В MFC 8,0 Константная версия этого метода была изменена на Return `const CObject*` вместо `const CObject*&` .  Это изменение было внесено, чтобы привести компилятор в соответствие со стандартом C++.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetNext` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a> Коблист:: prev

Возвращает элемент List, определенный параметром *rPosition*, а затем устанавливает *rPosition* в значение value предыдущей записи в списке.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение расположения, возвращаемое предыдущим `GetPrev` или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

Можно использовать `GetPrev` в цикле обратных итераций, если исходное расположение устанавливается с вызовом `GetTailPosition` или `Find` .

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если извлеченный элемент является первым в списке, новое значение *rPosition* устанавливается в NULL.

> [!NOTE]
> В MFC 8,0 Константная версия этого метода была изменена на Return `const CObject*` вместо `const CObject*&` .  Это изменение было внесено, чтобы привести компилятор в соответствие со стандартом C++.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetPrev` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a> Коблист:: DataSize

Возвращает число элементов списка.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в списке.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetSize` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR-size () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR-size () const;**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a> Коблист:: tail

Возвращает `CObject` указатель, представляющий элемент хвоста данного списка.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

Перед вызовом необходимо убедиться, что список не пуст `GetTail` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetTail` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& @ tail () const; void \*& @ tail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& @ tail () const; CString& "tail" ();**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a> Коблист:: Жеттаилпоситион

Возвращает расположение элемента хвоста в этом списке; **Значение NULL** , если список пуст.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetTailPosition` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Жеттаилпоситион () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Жеттаилпоситион () const;**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a> Коблист:: InsertAfter

Добавляет элемент в этот список после элемента в указанной позиции.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*position*<br/>
Значение расположения, возвращенное предыдущим `GetNext` `GetPrev` `Find` вызовом функции-члена, или.

*невелемент*<br/>
Указатель на объект, добавляемый в этот список.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::InsertAfter` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertAfter позиций (** *Расположение* **, void)** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Расположение InsertAfter (расположение расположения** *position* **, константа CString&** `newElement` **);**<br /><br /> **Расположение InsertAfter (расположение расположения** *position* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Возвращаемое значение

Значение расположения, которое совпадает с параметром " *позиционирование* ".

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a> Коблист:: методов insertBefore

Добавляет элемент в список перед элементом в указанной позиции.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*position*<br/>
Значение расположения, возвращенное предыдущим `GetNext` `GetPrev` `Find` вызовом функции-члена, или.

*невелемент*<br/>
Указатель на объект, добавляемый в этот список.

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::InsertBefore` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Методов insertBefore позиций (** *Расположение* **, void)** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Расположение методов insertBefore (расположение расположения** *position* **, константа CString&** `newElement` **);**<br /><br /> **Расположение методов insertBefore (расположение расположения** *position* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a> Коблист:: IsEmpty

Указывает, содержит ли этот список элементы.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот список пуст; в противном случае — 0.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::IsEmpty` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL-Empty () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL-Empty () const;**|

### <a name="example"></a>Пример

  См. пример для [RemoveAll](#removeall).

## <a name="coblistremoveall"></a><a name="removeall"></a> Коблист:: RemoveAll

Удаляет все элементы из этого списка и освобождает связанную `CObList` память.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Remarks

Если список уже пуст, то ошибка не создается.

При удалении элементов из удаляет `CObList` указатели объектов из списка. Вы несете ответственность за удаление самих объектов.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveAll` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a> Коблист:: RemoveAt

Удаляет указанный элемент из этого списка.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Параметры

*position*<br/>
Расположение элемента, удаляемого из списка.

### <a name="remarks"></a>Remarks

При удалении элемента из удаляется `CObList` указатель объекта из списка. Вы несете ответственность за удаление самих объектов.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (** *Расположение* расположения **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (** *Расположение* расположения **);**|

### <a name="example"></a>Пример

  Будьте внимательны при удалении элемента во время итерации списка. В следующем примере показан метод удаления, который гарантирует допустимость **POSITION** значения для метода [GetNext](#getnext).

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Результаты этой программы выглядят следующим образом:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a> Коблист:: Ремовехеад

Удаляет элемент из заголовка списка и возвращает указатель на него.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель, который ранее находился в `CObject` заголовке списка.

### <a name="remarks"></a>Remarks

Перед вызовом необходимо убедиться, что список не пуст `RemoveHead` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveHead` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void \* ремовехеад ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString Ремовехеад ();**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a> Коблист:: Ремоветаил

Удаляет элемент из заключительного фрагмента списка и возвращает указатель на него.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, находился в заключительном фрагменте списка.

### <a name="remarks"></a>Remarks

Перед вызовом необходимо убедиться, что список не пуст `RemoveTail` . Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveTail` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void \* ремоветаил ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString Ремоветаил ();**|

### <a name="example"></a>Пример

Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a> Коблист:: SetAt

Задает элемент в заданной позиции.

```cpp
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
РАСПОЛОЖЕНИЕ элемента, который необходимо задать.

*невелемент*<br/>
`CObject`Указатель, который должен быть записан в список.

### <a name="remarks"></a>Remarks

Переменная типа "расположение" является ключом для списка. Это не то же самое, что и индекс, и вы не можете самостоятельно обрабатывать значение позиции. `SetAt` записывает `CObject` указатель в указанную позиции в списке.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::SetAt` .

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (расположение** `pos` **, const CString&** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (расположение** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  Список класса см. в разделе [коблист:: коблист](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>См. также раздел

[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс Кстринглист](../../mfc/reference/cstringlist-class.md)<br/>
[Класс Кптрлист](../../mfc/reference/cptrlist-class.md)
