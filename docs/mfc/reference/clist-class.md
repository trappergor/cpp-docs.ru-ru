---
title: Класс CList
ms.date: 11/04/2016
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
ms.openlocfilehash: adc065687f0c2c40b7e66326ff9d1e6210a6962c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754128"
---
# <a name="clist-class"></a>Класс CList

Поддерживает упорядоченные списки неуникальных объектов, доступные последовательно или по значению.

## <a name="syntax"></a>Синтаксис

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Клист:Список](#clist)|Строит пустой упорядоченный список.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Клист::AddHead](#addhead)|Добавляет элемент (или все элементы в другом списке) к главе списка (делает новую голову).|
|[Клист:AddTail](#addtail)|Добавляет элемент (или все элементы в другом списке) к хвосту списка (делает новый хвост).|
|[Клист::Найти](#find)|Получает положение элемента, указанное значением указателя.|
|[Клист:FindIndex](#findindex)|Получает положение элемента, указанного индексом с нулевым уровнем.|
|[Клист:GetAt](#getat)|Получает элемент в заданной позиции.|
|[Клист:GetCount](#getcount)|Возвращает количество элементов в этом списке.|
|[Клист:GetHead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[Клист:GetHeadPosition](#getheadposition)|Возвращает положение головного элемента списка.|
|[Клист:GetNext](#getnext)|Получает следующий элемент для итерации.|
|[Клист:GetPrev](#getprev)|Получает предыдущий элемент для итерации.|
|[Клист::GetSize](#getsize)|Возвращает количество элементов в этом списке.|
|[Клист::GetTail](#gettail)|Возвращает хвостовой элемент списка (не может быть пустым).|
|[Клист:GetTailPosition](#gettailposition)|Возвращает положение хвостового элемента списка.|
|[Клист::ВставкаПосле](#insertafter)|Вставляет новый элемент после заданного положения.|
|[CList::InsertBefore](#insertbefore)|Вставляет новый элемент перед заданной позицией.|
|[Клист::Пустой](#isempty)|Тесты для состояния пустого списка (без элементов).|
|[Клист::RemoveAll](#removeall)|Удаляет все элементы из этого списка.|
|[Клист::RemoveAt](#removeat)|Удаляет элемент из этого списка, указанный позицией.|
|[Клист::Удалить](#removehead)|Удаляет элемент из главы списка.|
|[Клист::УдалитьХвост](#removetail)|Удаляет элемент из хвоста списка.|
|[Клист:SetAt](#setat)|Устанавливает элемент в заданной позиции.|

#### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип объекта, хранящийся в списке.

*ARG_TYPE*<br/>
Введите, используемый для ссылки на объекты, хранящиеся в списке. Может быть ссылкой.

## <a name="remarks"></a>Remarks

`CList`списки ведут себя как вдвойне связанные списки.

Переменная типа POSITION является ключом к списку. Вы можете использовать переменную POSITION в качестве итератора, чтобы последовательно пересекать список и в качестве закладки для удержания места. Однако позиция не является такой же, как индекс.

Элемент вставки очень быстро в списке голову, на хвосте, и на известном POSITION. Последовательный поиск необходим для поиска элемента по значению или индексу. Этот поиск может быть медленным, если список длинный.

Если вам нужна свалка отдельных элементов в списке, необходимо установить глубину контекста дампа до 1 или больше.

Некоторые функции членов этого класса вызывают функции глобального помощника, `CList` которые должны быть настроены для большинства видов использования класса. Смотрите [помощники класса коллекции](../../mfc/reference/collection-class-helpers.md) в разделе "Макрос и Глобалс".

Для получения дополнительной `CList`информации [Collections](../../mfc/collections.md)об использовании , см.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

## <a name="clistaddhead"></a><a name="addhead"></a>Клист::AddHead

Добавляет новый элемент или список элементов к главе этого списка.

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*newElement*<br/>
Новый элемент.

*pNewList*<br/>
Указатель на `CList` другой список. Элементы в *pNewList* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение POSITION вновь вставленного элемента.

### <a name="remarks"></a>Remarks

Список может быть пустым до операции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a>Клист:AddTail

Добавляет новый элемент или список элементов в хвост этого списка.

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*newElement*<br/>
Элемент, добавляемый в список.

*pNewList*<br/>
Указатель на `CList` другой список. Элементы в *pNewList* будут добавлены в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение POSITION вновь вставленного элемента.

### <a name="remarks"></a>Remarks

Список может быть пустым до операции.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a>Клист:Список

Строит пустой упорядоченный список.

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Детализация распределения памяти для расширения списка.

### <a name="remarks"></a>Remarks

По мере роста списка память распределяется в единицах записей *nBlockSize.*

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a>Клист::Найти

Поиск по списку последовательно, чтобы найти первый элемент, соответствующий указанному *searchValue.*

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Параметры

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*searchValue*<br/>
Значение, найденное в списке.

*startAfter*<br/>
Стартовая позиция для поиска. Если значение не указано, поиск начинается с головного элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если объект не найден.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a>Клист:FindIndex

Использует значение *nIndex* в качестве индекса в списке.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Нулевой индекс элемента списка, который можно найти.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если *nIndex* отрицательный или слишком большой.

### <a name="remarks"></a>Remarks

Он начинает последовательное сканирование от главы списка, останавливаясь на *n*th элемент.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a>Клист:GetAt

Получает элемент списка в заданной позиции.

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип объекта в списке.

*Позиции*<br/>
Положение в списке элемента, чтобы получить.

### <a name="return-value"></a>Возвращаемое значение

Посмотреть описание значения `GetHead`возврата для .

### <a name="remarks"></a>Remarks

`GetAt`возвращает элемент (или ссылку на элемент), связанный с данной позицией. Это не то же самое, что индекс, и вы не можете работать на стоимость POSITION себя. Переменная типа POSITION является ключом к списку.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

### <a name="example"></a>Пример

  Смотрите пример [для CList::GetHeadPosition](#getheadposition).

## <a name="clistgetcount"></a><a name="getcount"></a>Клист:GetCount

Получает количество элементов в этом списке.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащее количество элементов.

### <a name="remarks"></a>Remarks

Вызов этого метода будет генерировать тот же результат, что и метод [CList::GetSize.](#getsize)

### <a name="example"></a>Пример

  Смотрите пример [для CList::RemoveHead](#removehead).

## <a name="clistgethead"></a><a name="gethead"></a>Клист:GetHead

Получает головной элемент (или ссылку на головной элемент) этого списка.

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип объекта в списке.

### <a name="return-value"></a>Возвращаемое значение

Если список **конст**, `GetHead` возвращает копию элемента во главе списка. Это позволяет использовать функцию только на правой стороне оператора назначения и защищает список от модификации.

Если список не является `GetHead` **const**, возвращает ссылку на элемент во главе списка. Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Remarks

Вы должны убедиться, что список не пуст, прежде чем звонить `GetHead`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a>Клист:GetHeadPosition

Получает положение головного элемента этого списка.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a>Клист:GetNext

Получает элемент списка, идентифицированный *rPosition,* затем устанавливает *rPosition* к значению POSITION следующей записи в списке.

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов в списке.

*rPosition*<br/>
Ссылка на значение POSITION, `GetNext`возвращенное предыдущим, [GetHeadPosition](#getheadposition)или другим вызовом функции участника.

### <a name="return-value"></a>Возвращаемое значение

Если список **конст**, `GetNext` возвращает копию элемента списка. Это позволяет использовать функцию только на правой стороне оператора назначения и защищает список от модификации.

Если список не является `GetNext` **const**, возвращает ссылку на элемент списка. Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Remarks

Вы можете `GetNext` использовать в цикле передних итерации, если `GetHeadPosition` `Find`вы установите исходное положение с вызовом или .

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный элемент является последним в списке, `rPosition` то новое значение устанавливается в NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a>Клист:GetPrev

Получает элемент списка, `rPosition`идентифицированный, затем устанавливаетзначение `rPosition` POSITION предыдущей записи в списке.

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов в списке.

*rPosition*<br/>
Ссылка на значение POSITION, `GetPrev` возвращенное предыдущим или другим вызовом функции участника.

### <a name="return-value"></a>Возвращаемое значение

Если список **конст**, `GetPrev` возвращает копию элемента во главе списка. Это позволяет использовать функцию только на правой стороне оператора назначения и защищает список от модификации.

Если список не является `GetPrev` **const**, возвращает ссылку на элемент списка. Это позволяет использовать функцию по обе стороны оператора назначения и, таким образом, позволяет модифицировать записи списка.

### <a name="remarks"></a>Remarks

Вы можете `GetPrev` использовать в обратном цикле итерации, если `GetTailPosition` `Find`вы установите исходное положение с вызовом или .

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

Если извлеченный элемент является первым в списке, то новое значение *rPosition* устанавливается на NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a>Клист::GetSize

Возвращает количество элементов списка.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в списке.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в списке.  Вызов этого метода будет генерировать тот же результат, что и метод [CList::GetCount.](#getcount)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a>Клист::GetTail

Получает `CObject` указатель, представляющий элемент хвоста этого списка.

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов в списке.

### <a name="return-value"></a>Возвращаемое значение

Смотрите описание значения возврата для [GetHead.](../../mfc/reference/coblist-class.md#gethead)

### <a name="remarks"></a>Remarks

Вы должны убедиться, что список не пуст, прежде чем звонить `GetTail`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a>Клист:GetTailPosition

Получает положение хвостового элемента этого списка; NULL, если список пуст.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое может быть использовано для итерации или поиска указателя объекта; NULL, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a>Клист::ВставкаПосле

Добавляет элемент в этот список после элемента в указанном положении.

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Значение POSITION возвращается `GetNext`предыдущим `GetPrev`вызовом функции `Find` участника.

*ARG_TYPE*<br/>
Параметры шаблона, определяющие тип элемента списка.

*newElement*<br/>
Элемент, добавляемый в список.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое можно использовать для итерации или извлечения элемента списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a>Клист::Вставитьперед

Добавляет элемент в список перед элементом в указанной позиции.

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Значение POSITION возвращается `GetNext`предыдущим `GetPrev`вызовом функции `Find` участника.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*newElement*<br/>
Элемент, добавляемый в список.

### <a name="return-value"></a>Возвращаемое значение

Значение POSITION, которое можно использовать для итерации или извлечения элемента списка.

### <a name="remarks"></a>Remarks

Если *позиция* NULL, элемент вставляется во главе списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a>Клист::Пустой

Указывает, не содержит ли этот список элементов.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если этот список пуст; в противном случае 0.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a>Клист::RemoveAll

Удаляет все элементы из этого списка и освобождает связанную память.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Remarks

Ошибка не генерируется, если список уже пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a>Клист::RemoveAt

Удаляет указанный элемент из этого списка.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Параметры

*Позиции*<br/>
Положение элемента, который будет удален из списка.

### <a name="remarks"></a>Remarks

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a>Клист::Удалить

Удаляет элемент из головы списка и возвращает указатель к нему.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов в списке.

### <a name="return-value"></a>Возвращаемое значение

Элемент, ранее возглавляваемый списком.

### <a name="remarks"></a>Remarks

Вы должны убедиться, что список не пуст, прежде чем звонить `RemoveHead`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a>Клист::УдалитьХвост

Удаляет элемент из хвоста списка и возвращает указатель к нему.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметры шаблона, определяющие тип элементов в списке.

### <a name="return-value"></a>Возвращаемое значение

Элемент, который был в хвосте списка.

### <a name="remarks"></a>Remarks

Вы должны убедиться, что список не пуст, прежде чем звонить `RemoveTail`. Если список пуст, то версия Debug библиотеки класса Microsoft Foundation утверждает. Используйте [IsEmpty,](#isempty) чтобы убедиться, что список содержит элементы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a>Клист:SetAt

Переменная типа POSITION является ключом к списку.

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
POSITION элемента, который будет установлен.

*ARG_TYPE*<br/>
Параметр шаблона, указывающий тип элемента списка (может быть ссылкой).

*newElement*<br/>
Элемент, который будет добавлен в список.

### <a name="remarks"></a>Remarks

Это не то же самое, что индекс, и вы не можете работать на стоимость POSITION себя. `SetAt`записывает элемент в указанное положение в списке.

Необходимо убедиться, что значение POSITION представляет собой действительное положение в списке. Если она недействительна, то версия Debug библиотеки класса Microsoft Foundation утверждает.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMap](../../mfc/reference/cmap-class.md)<br/>
[Класс CArray](../../mfc/reference/carray-class.md)
