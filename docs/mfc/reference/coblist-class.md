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
ms.openlocfilehash: 2fc3a3643c675394de555f1411030e278bcee775
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855334"
---
# <a name="coblist-class"></a>Класс Коблист

Фсуппортс упорядоченные списки неуникальных `CObject` указателей, доступных последовательно или по значению указателя.

## <a name="syntax"></a>Синтаксис

```
class CObList : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Коблист:: Коблист](#coblist)|Конструирует пустой список для `CObject`ных указателей.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
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

списки `CObList` ведут себя как двунаправленные списки.

Переменная типа "расположение" является ключом для списка. Можно использовать переменную позиции как итератор для последовательного прохода по списку и как закладку для размещения. Однако позиция не совпадает с индексом.

Вставка элемента происходит очень быстро в заголовке списка, в хвосте и в известной позиции. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может выполняться медленно, если список длинный.

`CObList` включает макрос IMPLEMENT_SERIAL для поддержки сериализации и дампа его элементов. Если список `CObject`ных указателей хранится в архиве либо с перегруженным оператором вставки, либо с функцией-членом `Serialize`, каждый элемент `CObject` сериализуется в свою очередь.

Если требуется дамп отдельных элементов `CObject` в списке, необходимо установить глубину контекста дампа в 1 или более.

При удалении объекта `CObList` или удалении его элементов удаляются только `CObject`ные указатели, а не объекты, на которые они ссылаются.

Вы можете создавать собственные классы из `CObList`. Новый класс списка, предназначенный для хранения указателей на объекты, производные от `CObject`, добавляет новые элементы данных и новые функции элементов. Обратите внимание, что результирующий список не строго типизирован, так как он допускает вставку любого `CObject` указателя.

> [!NOTE]
>  Если предполагается сериализовать список, необходимо использовать макрос [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) в реализации производного класса.

Дополнительные сведения об использовании `CObList`см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

##  <a name="addhead"></a>Коблист:: Аддхеад

Добавляет новый элемент или список элементов в заголовок этого списка.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*невелемент*<br/>
`CObject`ный указатель, добавляемый в этот список.

*пневлист*<br/>
Указатель на другой список `CObList`. Элементы в *пневлист* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение расположения вновь вставленного элемента.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::AddHead`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**Аддхеад позиций (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void аддхеад (кптрлист** <strong>\*</strong> `pNewList` **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Расположение аддхеад (const CString &** `newElement` **);**<br /><br /> **Позиционирование аддхеад (LPCTSTR** `newElement` **);**<br /><br /> **void аддхеад (кстринглист** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Remarks

Перед операцией список может быть пустым.

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

##  <a name="addtail"></a>Коблист:: AddTail

Добавляет новый элемент или список элементов в конец этого списка.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*невелемент*<br/>
`CObject`ный указатель, добавляемый в этот список.

*пневлист*<br/>
Указатель на другой список `CObList`. Элементы в *пневлист* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение расположения вновь вставленного элемента.

### <a name="remarks"></a>Remarks

Перед операцией список может быть пустым.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::AddTail`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**AddTail позиций (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (кптрлист** <strong>\*</strong> `pNewList` **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Расположение AddTail (const CString &** `newElement` **);**<br /><br /> **Позиционирование AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (кстринглист** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

##  <a name="coblist"></a>Коблист:: Коблист

Конструирует пустой список указателей `CObject`.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*нблокксизе*<br/>
Гранулярность выделения памяти для расширения списка.

### <a name="remarks"></a>Remarks

По мере роста списка память выделяется в единицах *нблокксизе* записей. При сбое выделения памяти выдается `CMemoryException`.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::CObList`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**Кптрлист (INT_PTR** `nBlockSize` **= 10);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Кстринглист (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Пример

  Ниже приведен список классов, производных от `CObject``CAge` используемых во всех примерах коллекции:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Ниже приведен пример использования `CObList` конструктора:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

##  <a name="find"></a>Коблист:: Find

Выполняет поиск в списке последовательно, чтобы найти первый `CObject` указатель, соответствующий заданному `CObject` указателю.

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

В следующей таблице показаны другие функции элементов, аналогичные `CObList::Find`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**Поиск расположения (void** <strong>\*</strong> `searchValue` **, позицией** `startAfter` **= null) const;**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Поиск по положению (LPCTSTR** `searchValue` **, позиционирование** `startAfter` **= null) const;**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

##  <a name="findindex"></a>Коблист:: FindIndex

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

В следующей таблице показаны другие функции элементов, аналогичные `CObList::FindIndex`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**FindIndex (INT_PTR** `nIndex` **) const;**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

##  <a name="getat"></a>Коблист:: GetAt

Переменная типа "расположение" является ключом для списка.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*position*<br/>
Значение расположения, возвращенное предыдущим `GetHeadPosition` или `Find` вызова функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

Это не то же самое, что и индекс, и вы не можете самостоятельно обрабатывать значение позиции. `GetAt` извлекает указатель `CObject`, связанный с заданной позицией.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (** *положением* расположения **) const;**<br /><br /> **void\*& GetAt (** *Расположение* расположения **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (** *положением* расположения **) const;**<br /><br /> **CString & GetAt (** *Расположение* расположения **);**|

### <a name="example"></a>Пример

  См. пример для [FindIndex](#findindex).

##  <a name="getcount"></a>Коблист:: NOCOUNT

Возвращает число элементов в этом списке.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение, содержащее число элементов.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetCount`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**INT_PTR вычислить const ();**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**INT_PTR вычислить const ();**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

##  <a name="gethead"></a>Коблист:: onhead

Возвращает указатель `CObject`, представляющий головной элемент этого списка.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если доступ к списку осуществляется через указатель на `const CObList`, `GetHead` возвращает указатель `CObject`. Это позволяет использовать функцию только с правой стороны оператора присваивания и тем самым защищает список от изменения.

Если доступ к списку осуществляется напрямую или с помощью указателя на `CObList`, `GetHead` возвращает ссылку на указатель `CObject`. Это позволяет использовать функцию с любой стороны оператора присваивания и тем самым допустить изменение записей в списке.

### <a name="remarks"></a>Remarks

Перед вызовом `GetHead`необходимо убедиться, что список не пуст. Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetHead`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**const void\*&ом-Head () const; void\*&-Head ();**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**const CString &-Head () const; CString &-Head ();**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

В следующем примере показано использование `GetHead` в левой части оператора присваивания.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

##  <a name="getheadposition"></a>Коблист:: Жесеадпоситион

Возвращает расположение головного элемента этого списка.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetHeadPosition`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**Жесеадпоситион () const;**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Жесеадпоситион () const;**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

##  <a name="getnext"></a>Коблист:: GetNext

Возвращает элемент List, идентифицируемый *rPosition*, а затем задает для *rPosition* значение `POSITION` следующей записи в списке.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение значения value, возвращенное предыдущим `GetNext`, `GetHeadPosition`или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

`GetNext` можно использовать в цикле прямой итерации, если начальная позицией устанавливается с вызовом `GetHeadPosition` или `Find`.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если извлеченный элемент является последним в списке, новое значение *rPosition* устанавливается в NULL.

Элемент можно удалить во время итерации. См. пример для [RemoveAt](#removeat).

> [!NOTE]
>  Начиная с MFC 8,0, Константная версия этого метода изменилась так, чтобы возвращался `const CObject*` вместо `const CObject*&`.  Это изменение было внесено, чтобы привести компилятор в соответствие со C++ стандартом.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetNext`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

##  <a name="getprev"></a>Коблист:: prev

Возвращает элемент List, определенный параметром *rPosition*, а затем устанавливает *rPosition* в значение value предыдущей записи в списке.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылка на значение расположения, возвращенное предыдущим `GetPrev` или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

`GetPrev` можно использовать в цикле обратных итераций, если исходное расположение устанавливается с вызовом `GetTailPosition` или `Find`.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

Если извлеченный элемент является первым в списке, новое значение *rPosition* устанавливается в NULL.

> [!NOTE]
>  Начиная с MFC 8,0, Константная версия этого метода изменилась так, чтобы возвращался `const CObject*` вместо `const CObject*&`.  Это изменение было внесено, чтобы привести компилятор в соответствие со C++ стандартом.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetPrev`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

##  <a name="getsize"></a>Коблист:: DataSize

Возвращает число элементов списка.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в списке.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetSize`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**INT_PTR-size () const;**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**INT_PTR-size () const;**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

##  <a name="gettail"></a>Коблист:: tail

Возвращает указатель `CObject`, представляющий элемент хвоста этого списка.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Возвращаемое значение

См. описание возвращаемого значения для [onhead](#gethead).

### <a name="remarks"></a>Remarks

Перед вызовом `GetTail`необходимо убедиться, что список не пуст. Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetTail`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**const void\*&е "конст" () const; void\*&е "tail" ();**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**const CString & @ tail () const; CString & "tail" ();**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

##  <a name="gettailposition"></a>Коблист:: Жеттаилпоситион

Возвращает расположение элемента хвоста в этом списке; **Значение NULL** , если список пуст.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::GetTailPosition`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**Жеттаилпоситион () const;**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Жеттаилпоситион () const;**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

##  <a name="insertafter"></a>Коблист:: InsertAfter

Добавляет элемент в этот список после элемента в указанной позиции.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*position*<br/>
Значение расположения, возвращенное предыдущим `GetNext`, `GetPrev`или вызовом функции-члена `Find`.

*невелемент*<br/>
Указатель на объект, добавляемый в этот список.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::InsertAfter`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**InsertAfter позиций (** *расположение* **, void** <strong>\*</strong> `newElement` **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Расположение InsertAfter (расположение расположения** **, константа CString &** `newElement` **);**<br /><br /> **InsertAfter позиций (** *расположение* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Возвращаемое значение

Значение расположения, которое совпадает с параметром " *позиционирование* ".

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

##  <a name="insertbefore"></a>Коблист:: методов insertBefore

Добавляет элемент в список перед элементом в указанной позиции.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*position*<br/>
Значение расположения, возвращенное предыдущим `GetNext`, `GetPrev`или вызовом функции-члена `Find`.

*невелемент*<br/>
Указатель на объект, добавляемый в этот список.

### <a name="return-value"></a>Возвращаемое значение

Значение позиции, которое может использоваться для получения итераций или указателя на объект; Значение NULL, если список пуст.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::InsertBefore`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**Методов insertBefore позиций (** *расположение* **, void** <strong>\*</strong> `newElement` **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**Расположение методов insertBefore (расположение расположения** **, константа CString &** `newElement` **);**<br /><br /> **Методов insertBefore позиций (** *расположение* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

##  <a name="isempty"></a>Коблист:: IsEmpty

Указывает, содержит ли этот список элементы.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если этот список пуст; в противном случае — 0.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::IsEmpty`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**BOOL-Empty () const;**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**BOOL-Empty () const;**|

### <a name="example"></a>Пример

  См. пример для [RemoveAll](#removeall).

##  <a name="removeall"></a>Коблист:: RemoveAll

Удаляет все элементы из этого списка и освобождает связанную с ним `CObList` память.

```
void RemoveAll();
```

### <a name="remarks"></a>Remarks

Если список уже пуст, то ошибка не создается.

При удалении элементов из `CObList`удаляются указатели объектов из списка. Вы несете ответственность за удаление самих объектов.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveAll`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

##  <a name="removeat"></a>Коблист:: RemoveAt

Удаляет указанный элемент из этого списка.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Параметры

*position*<br/>
Расположение элемента, удаляемого из списка.

### <a name="remarks"></a>Remarks

При удалении элемента из `CObList`удаляется указатель объекта из списка. Вы несете ответственность за удаление самих объектов.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveAt`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (** *Расположение* расположения **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (** *Расположение* расположения **);**|

### <a name="example"></a>Пример

  Будьте внимательны при удалении элемента во время итерации списка. В следующем примере показан метод удаления, который гарантирует допустимость значения для метода [GetNext](#getnext).

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Результаты этой программы выглядят следующим образом:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

##  <a name="removehead"></a>Коблист:: Ремовехеад

Удаляет элемент из заголовка списка и возвращает указатель на него.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель `CObject`, ранее на заголовке списка.

### <a name="remarks"></a>Remarks

Перед вызовом `RemoveHead`необходимо убедиться, что список не пуст. Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveHead`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**void\* Ремовехеад ();**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**CString Ремовехеад ();**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

##  <a name="removetail"></a>Коблист:: Ремоветаил

Удаляет элемент из заключительного фрагмента списка и возвращает указатель на него.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, находился в заключительном фрагменте списка.

### <a name="remarks"></a>Remarks

Перед вызовом `RemoveTail`необходимо убедиться, что список не пуст. Если список пуст, то отладочная версия библиотека Microsoft Foundation Class утверждается. Используйте параметр [IsEmpty](#isempty) , чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::RemoveTail`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**void\* Ремоветаил ();**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**CString Ремоветаил ();**|

### <a name="example"></a>Пример

Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

##  <a name="setat"></a>Коблист:: SetAt

Задает элемент в заданной позиции.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
РАСПОЛОЖЕНИЕ элемента, который необходимо задать.

*невелемент*<br/>
Указатель `CObject`, записываемый в список.

### <a name="remarks"></a>Remarks

Переменная типа "расположение" является ключом для списка. Это не то же самое, что и индекс, и вы не можете самостоятельно обрабатывать значение позиции. `SetAt` записывает `CObject` указатель в указанную позиции в списке.

Необходимо убедиться, что значение координаты представляет допустимую точку в списке. Если он является недопустимым, отладочная версия библиотека Microsoft Foundation Class утверждается.

В следующей таблице показаны другие функции элементов, аналогичные `CObList::SetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[кптрлист](../../mfc/reference/cptrlist-class.md)|**void SetAt (расположение** `pos` **, const CString &** `newElement` **);**|
|[кстринглист](../../mfc/reference/cstringlist-class.md)|**void SetAt (позиционирование** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  Список `CAge` класса см. в разделе [коблист:: коблист](#coblist) .

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStringList](../../mfc/reference/cstringlist-class.md)<br/>
[Класс CPtrList](../../mfc/reference/cptrlist-class.md)
