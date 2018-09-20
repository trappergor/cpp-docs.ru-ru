---
title: Класс cObList | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbf635b2f6d07486a6a8961305e0b218b3c24926
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429686"
---
# <a name="coblist-class"></a>Класс cObList

упорядоченные списки неуникальный fSupports `CObject` указатели доступны последовательно или по значению указателей.

## <a name="syntax"></a>Синтаксис

```
class CObList : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CObList::CObList](#coblist)|Создается пустой список для `CObject` указатели.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CObList::AddHead](#addhead)|Добавляет элемент (или все элементы из другого списка) в начало списка (делает нового заголовка).|
|[CObList::AddTail](#addtail)|Добавляет в конец списка (делает новый tail) элемента (или все элементы из другого списка).|
|[CObList::Find](#find)|Получает положение элемента, определяемого значением указателя.|
|[CObList::FindIndex](#findindex)|Получает положение, определяемое отсчитываемый от нуля индекс элемента.|
|[CObList::GetAt](#getat)|Получает элемент в заданной позиции.|
|[CObList::GetCount](#getcount)|Возвращает количество элементов в этом списке.|
|[CObList::GetHead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[CObList::GetHeadPosition](#getheadposition)|Возвращает позицию головной элемент списка.|
|[CObList::GetNext](#getnext)|Получает следующий элемент для выполнения итерации.|
|[CObList::GetPrev](#getprev)|Возвращает предыдущий элемент для выполнения итерации.|
|[CObList::GetSize](#getsize)|Возвращает количество элементов в этом списке.|
|[CObList::GetTail](#gettail)|Возвращает заключительный фрагмент элемент списка (не может быть пустым).|
|[CObList::GetTailPosition](#gettailposition)|Возвращает позицию заключительного элемента списка.|
|[CObList::InsertAfter](#insertafter)|Вставляет новый элемент после заданной позиции.|
|[CObList::InsertBefore](#insertbefore)|Вставляет новый элемент до заданной позиции.|
|[CObList::IsEmpty](#isempty)|Проверяет условие пустой список (нет элементов).|
|[CObList::RemoveAll](#removeall)|Удаляет все элементы из этого списка.|
|[CObList::RemoveAt](#removeat)|Удаляет элемент из этого списка, указанного параметром position.|
|[CObList::RemoveHead](#removehead)|Удаляет элемент из головы списка.|
|[CObList::RemoveTail](#removetail)|Удаляет элемент из конца списка.|
|[CObList::SetAt](#setat)|Задает элемент в заданной позиции.|

## <a name="remarks"></a>Примечания

`CObList` списки ведут себя как взаимосвязанные списки.

Переменная типа ПОЗИЦИЯ — это ключ для списка. Можно использовать переменную ПОЗИЦИИ, и как итератор для просмотра списка последовательно и как закладку для хранения место. Позиция не так же, как индекс, однако.

Вставка элемента очень быстро, в начало списка, в копию заключительного фрагмента и известном положении. Последовательного поиска необходим для поиска элемента по значению или индексу. Этот поиск может быть медленным, если список длинный.

`CObList` включает в себя IMPLEMENT_SERIAL-макрос для поддержки сериализации и записи элементов в дамп. Если список `CObject` указатели хранится в архив с помощью перегруженного оператора вставки или `Serialize` функция-член, чтобы каждый `CObject` элемент сериализуется в свою очередь.

Если вам требуется дамп отдельных `CObject` элементов в списке, необходимо задать глубины контекста дампа 1 или более поздней версии.

Когда `CObList` объект удаляется или когда его элементы удаляются, только `CObject` будут удалены указатели, не объекты, они ссылаются.

Вы можете создавать собственные производные классы от `CObList`. Новый класс списка, предназначены для хранения указателей на объекты, производные от `CObject`, добавляет новые элементы данных и новых функций-членов. Обратите внимание на то, что полученный список не является строго типизированным, так как он позволяет выполнять вставку любого `CObject` указатель.

> [!NOTE]
>  Необходимо использовать [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) макрос в реализации в производном классе, если требуется выполнить сериализацию списка.

Дополнительные сведения об использовании `CObList`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

##  <a name="addhead"></a>  CObList::AddHead

Добавляет новый элемент или список элементов в заголовке этого списка.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*newElement*<br/>
`CObject` Указатель для добавления в этот список.

*pNewList*<br/>
Указатель на другую `CObList` списка. Элементы в *pNewList* будут добавляться в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение ПОЗИЦИИ вставленный элемент.

В следующей таблице показаны другой член функции, которые похожи на `CObList::AddHead`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЗИЦИЯ AddHead (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddHead (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЗИЦИЯ AddHead (const CString &** `newElement` **);**<br /><br /> **ПОЗИЦИЯ AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Примечания

Список может быть пустым, перед выполнением операции.

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Далее приведены результаты из этой программы.

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

##  <a name="addtail"></a>  CObList::AddTail

Добавляет новый элемент или список элементов в конец этого списка.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Параметры

*newElement*<br/>
`CObject` Указатель для добавления в этот список.

*pNewList*<br/>
Указатель на другую `CObList` списка. Элементы в *pNewList* будут добавляться в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение ПОЗИЦИИ вставленный элемент.

### <a name="remarks"></a>Примечания

Список может быть пустым, перед выполнением операции.

В следующей таблице показаны другой член функции, которые похожи на `CObList::AddTail`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**AddTail ПОЗИЦИИ (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**AddTail ПОЗИЦИИ (const CString &** `newElement` **);**<br /><br /> **AddTail ПОЗИЦИИ (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Далее приведены результаты из этой программы.

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

##  <a name="coblist"></a>  CObList::CObList

Создает пустой `CObject` список указателей.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Гранулярность выделения памяти для расширения списка.

### <a name="remarks"></a>Примечания

По мере роста списке память выделяется в единицах *nBlockSize* записей. Если не удается выделить память, `CMemoryException` возникает исключение.

В следующей таблице показаны другой член функции, которые похожи на `CObList::CObList`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Пример

  Ниже приведен перечень `CObject`-производный класс `CAge` используется во всех примерах коллекции:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Ниже приведен пример `CObList` использования конструктора:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

##  <a name="find"></a>  CObList::Find

В списке последовательно, чтобы найти первый `CObject` указатель, совпадающий с указанным ключом `CObject` указатель.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Параметры

*searchValue*<br/>
Указатель на объект, который требуется найти в этом списке.

*startAfter*<br/>
Начальное положение для поиска.

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации или извлечения указатель объекта; Значение NULL, если объект не найден.

### <a name="remarks"></a>Примечания

Обратите внимание, что сравниваются значения указателя, а не содержимое объектов.

В следующей таблице показаны другой член функции, которые похожи на `CObList::Find`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Найти ПОЗИЦИЮ (void** <strong>\*</strong> `searchValue` **, положение** `startAfter` **= NULL) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Найти ПОЗИЦИИ (LPCTSTR** `searchValue` **, положение** `startAfter` **= NULL) const;**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

##  <a name="findindex"></a>  CObList::FindIndex

Использует значение *nIndex* как индекс в списке.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс элемента списка, который требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации или извлечения указатель объекта; Значение NULL, если *nIndex* слишком велик. (Платформа создает утверждение, если *nIndex* является отрицательным.)

### <a name="remarks"></a>Примечания

Началом последовательного проверки из головы списке остановка на *n*элемент th.

В следующей таблице показаны другой член функции, которые похожи на `CObList::FindIndex`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЗИЦИЯ FindIndex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЗИЦИЯ FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

##  <a name="getat"></a>  CObList::GetAt

Переменная типа ПОЗИЦИЯ — это ключ для списка.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*положение*<br/>
Значение ПОЗИЦИИ, возвращенное предыдущим `GetHeadPosition` или `Find` вызова функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. в описании возвращаемое значение для [GetHead](#gethead).

### <a name="remarks"></a>Примечания

Это не так же, как индекс, и вы не можете работать значение ПОЗИЦИИ самостоятельно. `GetAt` Извлекает `CObject` указатель, связанный с заданной позиции.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (ПОЗИЦИЯ** *позиции* **) const;**<br /><br /> **void\*& GetAt (ПОЗИЦИЯ** *позиции* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (ПОЗИЦИЯ** *позиции* **) const;**<br /><br /> **CString & GetAt (ПОЗИЦИЯ** *позиции* **);**|

### <a name="example"></a>Пример

  См. в примере [FindIndex](#findindex).

##  <a name="getcount"></a>  CObList::GetCount

Возвращает количество элементов в этом списке.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Целое значение, содержащее количество элементов.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetCount`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; INT_PTR GetCount)**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; INT_PTR GetCount)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

##  <a name="gethead"></a>  CObList::GetHead

Получает `CObject` указатель, представляющий элемент заголовка этого списка.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Возвращаемое значение

Если список осуществляется через указатель на `const CObList`, затем `GetHead` возвращает `CObject` указатель. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.

Если список осуществляется напрямую или через указатель в `CObList`, затем `GetHead` возвращает ссылку на `CObject` указатель. Это позволяет функции для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `GetHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetHead`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& () GetHead const; void\*& GetHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString & GetHead ();**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

Следующий пример иллюстрирует использование `GetHead` в левой части оператора присваивания.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

##  <a name="getheadposition"></a>  CObList::GetHeadPosition

Получает положение головной элемент этого списка.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации или извлечения указатель объекта; Значение NULL, если список пуст.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetHeadPosition`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; ПОЗИЦИЯ GetHeadPosition)**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; ПОЗИЦИЯ GetHeadPosition)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

##  <a name="getnext"></a>  CObList::GetNext

Получает элемент списка, идентифицируемый *rPosition*, затем задает *rPosition* для `POSITION` значения следующую запись в списке.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetNext`, `GetHeadPosition`, или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. в описании возвращаемое значение для [GetHead](#gethead).

### <a name="remarks"></a>Примечания

Можно использовать `GetNext` в цикле прямой итерации, если установить начальное положение, с помощью вызова `GetHeadPosition` или `Find`.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Если полученного элемента является последним в списке, то новое значение *rPosition* имеет значение NULL.

Существует возможность удалить элемент во время итерации. См. в примере [RemoveAt](#removeat).

> [!NOTE]
>  Начиная с MFC 8.0 после изменения const версии этого метода для возврата `const CObject*` вместо `const CObject*&`.  Это изменение было внесено, чтобы привести в соответствие со стандартом языка C++ компилятор.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetNext`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Далее приведены результаты из этой программы.

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

##  <a name="getprev"></a>  CObList::GetPrev

Получает элемент списка, идентифицируемый *rPosition*, затем задает *rPosition* значению положение предыдущего элемента в списке.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetPrev` или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

См. в описании возвращаемое значение для [GetHead](#gethead).

### <a name="remarks"></a>Примечания

Можно использовать `GetPrev` в цикле обратной итерации, если установить начальное положение, с помощью вызова `GetTailPosition` или `Find`.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Если полученного элемента является первым в списке, выберите новое значение *rPosition* имеет значение NULL.

> [!NOTE]
>  Начиная с MFC 8.0 после изменения const версии этого метода для возврата `const CObject*` вместо `const CObject*&`.  Это изменение было внесено, чтобы привести в соответствие со стандартом языка C++ компилятор.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetPrev`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Далее приведены результаты из этой программы.

```Output
a CAge at $421C 21
a CAge at $421C 40
```

##  <a name="getsize"></a>  CObList::GetSize

Возвращает количество элементов списка.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в списке.

### <a name="remarks"></a>Примечания

Этот метод используется для получения числа элементов в списке.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetSize`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; INT_PTR GetSize)**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; INT_PTR GetSize)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

##  <a name="gettail"></a>  CObList::GetTail

Получает `CObject` указатель, который представляет элемент заключительного этого списка.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Возвращаемое значение

См. в описании возвращаемое значение для [GetHead](#gethead).

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `GetTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetTail`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& () GetTail const; void\*& GetTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString & GetTail ();**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

##  <a name="gettailposition"></a>  CObList::GetTailPosition

Получает положение элемента заключительного этого списка. **NULL** Если список пуст.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации или извлечения указатель объекта; Значение NULL, если список пуст.

В следующей таблице показаны другой член функции, которые похожи на `CObList::GetTailPosition`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; ПОЗИЦИЯ GetTailPosition)**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; ПОЗИЦИЯ GetTailPosition)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

##  <a name="insertafter"></a>  CObList::InsertAfter

Добавляет элемент в этот список после элемента в указанной позиции.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*положение*<br/>
Значение ПОЗИЦИИ, возвращенное предыдущим `GetNext`, `GetPrev`, или `Find` вызова функции-члена.

*newElement*<br/>
Указатель на объект, добавляемый в этот список.

В следующей таблице показаны другой член функции, которые похожи на `CObList::InsertAfter`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЗИЦИЯ InsertAfter (ПОЗИЦИЯ** *позиции* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЗИЦИЯ InsertAfter (ПОЗИЦИЯ** *позиции* **, const CString &** `newElement` **);**<br /><br /> **ПОЗИЦИЯ InsertAfter (ПОЗИЦИЯ** *позиции* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, так как *позиции* параметра.

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Далее приведены результаты из этой программы.

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

##  <a name="insertbefore"></a>  CObList::InsertBefore

Добавляет элемент в список перед элементом в указанной позиции.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*положение*<br/>
Значение ПОЗИЦИИ, возвращенное предыдущим `GetNext`, `GetPrev`, или `Find` вызова функции-члена.

*newElement*<br/>
Указатель на объект, добавляемый в этот список.

### <a name="return-value"></a>Возвращаемое значение

Значение ПОЗИЦИИ, который может использоваться для итерации или извлечения указатель объекта; Значение NULL, если список пуст.

В следующей таблице показаны другой член функции, которые похожи на `CObList::InsertBefore`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**ПОЗИЦИЯ InsertBefore (ПОЗИЦИЯ** *позиции* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**ПОЗИЦИЯ InsertBefore (ПОЗИЦИЯ** *позиции* **, const CString &** `newElement` **);**<br /><br /> **ПОЗИЦИЯ InsertBefore (ПОЗИЦИЯ** *позиции* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Далее приведены результаты из этой программы.

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

##  <a name="isempty"></a>  CObList::IsEmpty

Указывает, является ли этот список не содержит элементов.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если список пуст; в противном случае 0.

В следующей таблице показаны другой член функции, которые похожи на `CObList::IsEmpty`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**(Const; BOOL IsEmpty)**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**(Const; BOOL IsEmpty)**|

### <a name="example"></a>Пример

  См. в примере [RemoveAll](#removeall).

##  <a name="removeall"></a>  CObList::RemoveAll

Удаляет все элементы из этого списка и освобождает связанного `CObList` памяти.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Сообщение об ошибке не создается в том случае, если список уже пуст.

При удалении элементов из `CObList`, удалите указателей объектов из списка. Это необходимо удалить сами объекты.

В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveAll`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void (RemoveAll);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void (RemoveAll);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

##  <a name="removeat"></a>  CObList::RemoveAt

Удаляет указанный элемент из этого списка.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Параметры

*положение*<br/>
Позиция элемента, который требуется удалить из списка.

### <a name="remarks"></a>Примечания

При удалении элемента из `CObList`, удалите указатель на объект из списка. Это необходимо удалить сами объекты.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (ПОЗИЦИЯ** *позиции* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (ПОЗИЦИЯ** *позиции* **);**|

### <a name="example"></a>Пример

  Будьте внимательны при удалении элемента во время итерации списка. В следующем примере показан способ удаления, гарантирующий является допустимым **ПОЗИЦИИ** значение [GetNext](#getnext).

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Далее приведены результаты из этой программы.

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

##  <a name="removehead"></a>  CObList::RemoveHead

Удаляет элемент из головы списка и возвращает указатель на него.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Возвращаемое значение

`CObject` Указатель ранее в начало списка.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `RemoveHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveHead`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

##  <a name="removetail"></a>  CObList::RemoveTail

Удаляет элемент из конца списка и возвращает указатель на него.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект, который находился в конец списка.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `RemoveTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](#isempty) чтобы убедиться, что список содержит элементы.

В следующей таблице показаны другой член функции, которые похожи на `CObList::RemoveTail`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

##  <a name="setat"></a>  CObList::SetAt

Задает элемент в заданной позиции.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
ПОЗИЦИЯ элемента, который требуется задать.

*newElement*<br/>
`CObject` Указатель для записи в список.

### <a name="remarks"></a>Примечания

Переменная типа ПОЗИЦИЯ — это ключ для списка. Это не так же, как индекс, и вы не можете работать значение ПОЗИЦИИ самостоятельно. `SetAt` Записывает `CObject` указатель на указанной позиции в списке.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

В следующей таблице показаны другой член функции, которые похожи на `CObList::SetAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (ПОЗИЦИЯ** `pos` **, const CString &** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (ПОЗИЦИЯ** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Пример

  См. в разделе [CObList::CObList](#coblist) список `CAge` класса.

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Далее приведены результаты из этой программы.

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CStringList](../../mfc/reference/cstringlist-class.md)<br/>
[Класс CPtrList](../../mfc/reference/cptrlist-class.md)
