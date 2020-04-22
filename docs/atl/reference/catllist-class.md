---
title: Класс CAtlList
ms.date: 11/04/2016
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
ms.openlocfilehash: 0e4ea8eef51431c100f5d3119d7f75e9673e276e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748736"
---
# <a name="catllist-class"></a>Класс CAtlList

Этот класс предоставляет методы создания и управления объектом списка.

## <a name="syntax"></a>Синтаксис

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип элемента.

*ETraits*<br/>
Код, используемый для копирования или перемещения элементов. Более подробную информацию можно узнать в [классе CElementTraits.](../../atl/reference/celementtraits-class.md)

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAtlList::INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlList::CAtlList](#catllist)|Конструктор.|
|[CAtlList:::CAtlList](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlList::AddHead](#addhead)|Вызовите этот метод, чтобы добавить элемент в главу списка.|
|[CAtlList:AddHeadList](#addheadlist)|Вызовите этот метод, чтобы добавить существующий список в главу списка.|
|[CAtlList::AddTail](#addtail)|Вызовите этот метод, чтобы добавить элемент в хвост этого списка.|
|[CAtlList:AddTailList](#addtaillist)|Вызовите этот метод, чтобы добавить существующий список в хвост этого списка.|
|[CAtlList:AssertValid](#assertvalid)|Вызов этого метода, чтобы подтвердить список является действительным.|
|[CAtlList::Найти](#find)|Вызовите этот метод для поиска списка для указанного элемента.|
|[CAtlList:FindIndex](#findindex)|Назовите этот метод, чтобы получить положение элемента, учитывая значение индекса.|
|[CAtlList::GetAt](#getat)|Вызовите этот метод, чтобы вернуть элемент в указанной позиции в списке.|
|[CAtlList:GetCount](#getcount)|Вызовите этот метод, чтобы вернуть количество объектов в списке.|
|[CAtlList::GetHead](#gethead)|Вызовите этот метод, чтобы вернуть элемент во главе списка.|
|[CAtlList::GetHeadPosition](#getheadposition)|Назовите этот метод, чтобы получить должность руководителя списка.|
|[CAtlList::GetNext](#getnext)|Вызовите этот метод, чтобы вернуть следующий элемент из списка.|
|[CAtlList::GetPrev](#getprev)|Вызовите этот метод, чтобы вернуть предыдущий элемент из списка.|
|[CAtlList::GetTail](#gettail)|Вызовите этот метод, чтобы вернуть элемент в хвосте списка.|
|[CAtlList::GetTailPosition](#gettailposition)|Вызовите этот метод, чтобы получить положение хвоста списка.|
|[CAtlList::InsertAfter](#insertafter)|Вызовите этот метод, чтобы вставить новый элемент в список после указанной позиции.|
|[CAtlList::InsertBefore](#insertbefore)|Вызовите этот метод, чтобы вставить новый элемент в список перед указанной позицией.|
|[CAtlList::IsEmpty](#isempty)|Вызовите этот метод, чтобы определить, пусто ли список.|
|[CAtllist::MoveTohead](#movetohead)|Вызовите этот метод, чтобы переместить указанный элемент в главу списка.|
|[CAtllist::MoveToTail](#movetotail)|Вызовите этот метод, чтобы переместить указанный элемент в хвост списка.|
|[CAtllist::RemoveAll](#removeall)|Вызовите этот метод, чтобы удалить все элементы из списка.|
|[CAtllist::RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить один элемент из списка.|
|[CAtllist::RemoveHead](#removehead)|Вызовите этот метод, чтобы удалить элемент во главе списка.|
|[CAtllist::RemoveHeadNoReturn](#removeheadnoreturn)|Вызовите этот метод, чтобы удалить элемент во главе списка, не возвращая значение.|
|[CAtlList::RemoveTail](#removetail)|Вызовите этот метод, чтобы удалить элемент в хвосте списка.|
|[CAtllist::RemoveTailNoReturn](#removetailnoreturn)|Вызовите этот метод, чтобы удалить элемент в хвосте списка, не возвращая значение.|
|[CAtlList::SetAt](#setat)|Вызовите этот метод, чтобы установить значение элемента в заданной позиции в списке.|
|[CAtlList:SwapElements](#swapelements)|Вызовите этот метод для замены элементов в списке.|

## <a name="remarks"></a>Remarks

Класс `CAtlList` поддерживает упорядоченные списки неуникальных объектов, доступных последовательно или по стоимости. `CAtlList`списки ведут себя как вдвойне связанные списки. Каждый список имеет голову и хвост, и новые элементы (или списки в некоторых случаях) могут быть добавлены к концу списка, или вставлены до или после конкретных элементов.

Большинство методов `CAtlList` используют значение позиции. Это значение используется методами для ссылки на фактическое местоположение памяти, где хранятся элементы, и не должно быть рассчитано или предсказано напрямую. Если необходимо получить доступ к *элементу n*th в списке, метод [CAtlList::FindIndex](#findindex) вернет соответствующее значение позиции для данного индекса. Методы [CAtlList::GetNext](#getnext) и [CAtlList::GetPrev](#getprev) можно использовать для итерировать объекты в списке.

Для получения дополнительной информации о классах [ATL Collection Classes](../../atl/atl-collection-classes.md)коллекции, доступных с ATL, см.

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="catllistaddhead"></a><a name="addhead"></a>CAtlList::AddHead

Вызовите этот метод, чтобы добавить элемент в главу списка.

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Новый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает положение недавно добавленного элемента.

### <a name="remarks"></a>Remarks

При использовании первой версии с помощью конструктора по умолчанию создается пустой элемент, а не конструктор копии.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

## <a name="catllistaddheadlist"></a><a name="addheadlist"></a>CAtlList:AddHeadList

Вызовите этот метод, чтобы добавить существующий список в главу списка.

```cpp
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Параметры

*plNew*<br/>
Список, в который добавляется элемент.

### <a name="remarks"></a>Remarks

Список, указанный *plNew,* вставляется в начале существующего списка. В отладке сборки происходит сбой утверждения, если *plNew* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

## <a name="catllistaddtail"></a><a name="addtail"></a>CAtlList::AddTail

Вызовите этот метод, чтобы добавить элемент в хвост этого списка.

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Добавляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает POSITION недавно добавленного элемента.

### <a name="remarks"></a>Remarks

При использовании первой версии с помощью конструктора по умолчанию создается пустой элемент, а не конструктор копии. Элемент добавляется к концу списка, и теперь он становится хвостом. Этот метод можно использовать с пустым списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

## <a name="catllistaddtaillist"></a><a name="addtaillist"></a>CAtlList:AddTailList

Вызовите этот метод, чтобы добавить существующий список в хвост этого списка.

```cpp
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Параметры

*plNew*<br/>
Список, в который добавляется элемент.

### <a name="remarks"></a>Remarks

Список, указанный *plNew,* вставляется после последнего элемента (если такового имеется) в объект списка. Таким образом, последний элемент в *списке plNew* становится хвостом. В отладке сборки происходит сбой утверждения, если *plNew* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

## <a name="catllistassertvalid"></a><a name="assertvalid"></a>CAtlList:AssertValid

Вызов этого метода, чтобы подтвердить список является действительным.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Remarks

В отладке сборки происходит сбой утверждения, если объект списка недействителен. Чтобы быть действительным, пустой список должен иметь как голову, так и хвост, указывающий на NULL, а список, который не пуст, должен иметь как голову, так и хвост, указывающий на действительные адреса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

## <a name="catllistcatllist"></a><a name="catllist"></a>CAtlList::CAtlList

Конструктор.

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Remarks

Конструктор для `CAtlList` объекта. Размер блока — это мера объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

## <a name="catllistcatllist"></a><a name="dtor"></a>CAtlList:::CAtlList

Деструктор

```
~CAtlList() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы, включая звонок [в CAtlList::RemoveAll,](#removeall) чтобы удалить все элементы из списка.

В сборках отладок произойдет сбой утверждения, если список `RemoveAll`по-прежнему содержит некоторые элементы после вызова.

## <a name="catllistfind"></a><a name="find"></a>CAtlList::Найти

Вызовите этот метод для поиска списка для указанного элемента.

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Элемент, который можно найти в списке.

*posStartAfter*<br/>
Стартовая позиция для поиска. Если значение не указано, поиск начинается с головного элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение POSITION элемента, если найдено, в противном случае возвращает NULL.

### <a name="remarks"></a>Remarks

В отладке сборки происходит сбой утверждения, если объект списка недействителен, или если значение *posStartAfter* находится вне диапазона.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

## <a name="catllistfindindex"></a><a name="findindex"></a>CAtlList:FindIndex

Назовите этот метод, чтобы получить положение элемента, учитывая значение индекса.

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Индекс нулевой основе требуемого элемента списка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает соответствующее значение POSITION, или NULL, если *iElement* находится вне диапазона.

### <a name="remarks"></a>Remarks

Этот метод возвращает POSITION, соответствующий заданного значения индекса, что позволяет получить доступ к элементу *n*th в списке.

В отладке сборки происходит сбой утверждения, если объект списка недействителен.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

## <a name="catllistgetat"></a><a name="getat"></a>CAtlList::GetAt

Вызовите этот метод, чтобы вернуть элемент в указанной позиции в списке.

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение POSITION, определяющее определенный элемент.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент или копия.

### <a name="remarks"></a>Remarks

Если список **конст,** `GetAt` возвращает копию элемента. Это позволяет использовать метод только на правой стороне оператора назначения и защищает список от модификации.

Если список не **конст,** `GetAt` возвращает ссылку на элемент. Это позволяет использовать метод по обе стороны оператора назначения и, таким образом, позволяет изменить записи списка.

В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

Смотрите пример [CAtlList:FindIndex](#findindex).

## <a name="catllistgetcount"></a><a name="getcount"></a>CAtlList:GetCount

Вызовите этот метод, чтобы вернуть количество объектов в списке.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в списке.

### <a name="example"></a>Пример

Смотрите пример [для CAtlList::Найти](#find).

## <a name="catllistgethead"></a><a name="gethead"></a>CAtlList::GetHead

Вызовите этот метод, чтобы вернуть элемент во главе списка.

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку или копию элемента во главе списка.

### <a name="remarks"></a>Remarks

Если список **конст**, `GetHead` возвращает копию элемента во главе списка. Это позволяет использовать метод только на правой стороне оператора назначения и защищает список от модификации.

Если список не является `GetHead` **const**, возвращает ссылку на элемент во главе списка. Это позволяет использовать метод по обе стороны оператора назначения и, таким образом, позволяет изменить записи списка.

В сборках отладки произойдет сбой утверждения, если руководитель списка указывает на NULL.

### <a name="example"></a>Пример

Смотрите пример [CAtlList::AddHead](#addhead).

## <a name="catllistgetheadposition"></a><a name="getheadposition"></a>CAtlList::GetHeadPosition

Назовите этот метод, чтобы получить должность руководителя списка.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение POSITION, соответствующее элементу во главе списка.

### <a name="remarks"></a>Remarks

Если список пуст, возвращенное значение является NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

## <a name="catllistgetnext"></a><a name="getnext"></a>CAtlList::GetNext

Вызовите этот метод, чтобы вернуть следующий элемент из списка.

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение POSITION, возвращенное предыдущим `GetNext`вызовом [в, CAtlList::GetHeadPosition](#getheadposition)или другим `CAtlList` методом.

### <a name="return-value"></a>Возвращаемое значение

Если список **конст,** `GetNext` возвращает копию следующего элемента списка. Это позволяет использовать метод только на правой стороне оператора назначения и защищает список от модификации.

Если список не **конст,** `GetNext` возвращает ссылку на следующий элемент списка. Это позволяет использовать метод по обе стороны оператора назначения и, таким образом, позволяет изменить записи списка.

### <a name="remarks"></a>Remarks

Счетчик POSITION, *pos*, обновляется, чтобы указать на следующий элемент в списке, или NULL, если нет больше элементов. В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

Смотрите пример [CAtlList::GetHeadPosition](#getheadposition).

## <a name="catllistgetprev"></a><a name="getprev"></a>CAtlList::GetPrev

Вызовите этот метод, чтобы вернуть предыдущий элемент из списка.

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение POSITION, возвращенное предыдущим `GetPrev`вызовом [в, CAtlList::GetTailPosition](#gettailposition)или другим `CAtlList` методом.

### <a name="return-value"></a>Возвращаемое значение

Если список **конст**, `GetPrev` возвращает копию элемента списка. Это позволяет использовать метод только на правой стороне оператора назначения и защищает список от модификации.

Если список не является `GetPrev` **const**, возвращает ссылку на элемент списка. Это позволяет использовать метод по обе стороны оператора назначения и, таким образом, позволяет изменить записи списка.

### <a name="remarks"></a>Remarks

Счетчик POSITION, *pos*, обновляется, чтобы указать на предыдущий элемент в списке, или NULL, если нет больше элементов. В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

Смотрите пример [для CAtlList::GetTailPosition](#gettailposition).

## <a name="catllistgettail"></a><a name="gettail"></a>CAtlList::GetTail

Вызовите этот метод, чтобы вернуть элемент в хвосте списка.

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку или копию элемента в хвосте списка.

### <a name="remarks"></a>Remarks

Если список **конст**, `GetTail` возвращает копию элемента во главе списка. Это позволяет использовать метод только на правой стороне оператора назначения и защищает список от модификации.

Если список не является `GetTail` **const**, возвращает ссылку на элемент во главе списка. Это позволяет использовать метод по обе стороны оператора назначения и, таким образом, позволяет изменить записи списка.

В сборках отладки произойдет сбой утверждения, если хвост списка указывает на NULL.

### <a name="example"></a>Пример

Смотрите пример [для CAtlList::AddTail](#addtail).

## <a name="catllistgettailposition"></a><a name="gettailposition"></a>CAtlList::GetTailPosition

Вызовите этот метод, чтобы получить положение хвоста списка.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение POSITION, соответствующее элементу в хвосте списка.

### <a name="remarks"></a>Remarks

Если список пуст, возвращенное значение является NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

## <a name="catllistinargtype"></a><a name="inargtype"></a>CAtlList::INARGTYPE

Тип, используемый при передаваемом элементе в качестве входиного аргумента.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catllistinsertafter"></a><a name="insertafter"></a>CAtlList::InsertAfter

Вызовите этот метод, чтобы вставить новый элемент в список после указанной позиции.

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение POSITION, после которого будет вставлен новый элемент.

*Элемент*<br/>
Элемент, который будет вставлен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение POSITION нового элемента.

### <a name="remarks"></a>Remarks

В сборках отладок произойдет сбой утверждения, если список недействителен, если вставка не сбой, или если будет сделана попытка вставить элемент после хвоста.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

## <a name="catllistinsertbefore"></a><a name="insertbefore"></a>CAtlList::InsertBefore

Вызовите этот метод, чтобы вставить новый элемент в список перед указанной позицией.

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Новый элемент будет вставлен в список до этого значения POSITION.

*Элемент*<br/>
Элемент, который будет вставлен.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение POSITION нового элемента.

### <a name="remarks"></a>Remarks

В отладке сборки происходит сбой утверждения, если список недействителен, если вставка не работает, или если предпринимается попытка вставить элемент перед головой.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

## <a name="catllistisempty"></a><a name="isempty"></a>CAtlList::IsEmpty

Вызовите этот метод, чтобы определить, пусто ли список.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает верно, если список не содержит объектов, в противном случае ложные.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

## <a name="catllistmovetohead"></a><a name="movetohead"></a>CAtllist::MoveTohead

Вызовите этот метод, чтобы переместить указанный элемент в главу списка.

```cpp
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
ЗНАЧЕНИЕ POSITION элемента для перемещения.

### <a name="remarks"></a>Remarks

Указанный элемент перемещается из текущего положения в главу списка. В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

## <a name="catllistmovetotail"></a><a name="movetotail"></a>CAtllist::MoveToTail

Вызовите этот метод, чтобы переместить указанный элемент в хвост списка.

```cpp
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
ЗНАЧЕНИЕ POSITION элемента для перемещения.

### <a name="remarks"></a>Remarks

Указанный элемент перемещается из текущего положения в хвост списка. В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

Смотрите пример [CAtlList::MoveToHead](#movetohead).

## <a name="catllistremoveall"></a><a name="removeall"></a>CAtllist::RemoveAll

Вызовите этот метод, чтобы удалить все элементы из списка.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Remarks

Этот метод удаляет все элементы из списка и освобождает выделенную память. В сборках отладок будет поднят ATLASSERT, если все элементы не будут удалены или если структура списка повреждена.

### <a name="example"></a>Пример

Смотрите пример [для CAtlList::IsEmpty](#isempty).

## <a name="catllistremoveat"></a><a name="removeat"></a>CAtllist::RemoveAt

Вызовите этот метод, чтобы удалить один элемент из списка.

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение POSITION элемента для удаления.

### <a name="remarks"></a>Remarks

Элемент, на который ссылается *pos,* удаляется, а память освобождается. Допустимо использовать `RemoveAt` для удаления головы или хвоста списка.

В отладке сборки происходит сбой утверждения, если список недействителен или если удаление элемента приводит к доступу к памяти, которая не является частью структуры списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

## <a name="catllistremovehead"></a><a name="removehead"></a>CAtllist::RemoveHead

Вызовите этот метод, чтобы удалить элемент во главе списка.

```
E RemoveHead();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент во главе списка.

### <a name="remarks"></a>Remarks

Элемент головы удаляется из списка, и память освобождается. Возвращается копия элемента. В отладке сборки происходит сбой утверждения, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

## <a name="catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a>CAtllist::RemoveHeadNoReturn

Вызовите этот метод, чтобы удалить элемент во главе списка, не возвращая значение.

```cpp
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>Remarks

Элемент головы удаляется из списка, и память освобождается. В отладке сборки происходит сбой утверждения, если список пуст.

### <a name="example"></a>Пример

Смотрите пример [для CAtlList::IsEmpty](#isempty).

## <a name="catllistremovetail"></a><a name="removetail"></a>CAtlList::RemoveTail

Вызовите этот метод, чтобы удалить элемент в хвосте списка.

```
E RemoveTail();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент в хвосте списка.

### <a name="remarks"></a>Remarks

Элемент хвоста удаляется из списка, и память освобождается. Возвращается копия элемента. В отладке сборки происходит сбой утверждения, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

## <a name="catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a>CAtllist::RemoveTailNoReturn

Вызовите этот метод, чтобы удалить элемент в хвосте списка, не возвращая значение.

```cpp
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>Remarks

Элемент хвоста удаляется из списка, и память освобождается. В отладке сборки происходит сбой утверждения, если список пуст.

### <a name="example"></a>Пример

Смотрите пример [для CAtlList::IsEmpty](#isempty).

## <a name="catllistsetat"></a><a name="setat"></a>CAtlList::SetAt

Вызовите этот метод, чтобы установить значение элемента в заданной позиции в списке.

```cpp
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Значение POSITION, соответствующее изменению элемента.

*Элемент*<br/>
Значение нового элемента.

### <a name="remarks"></a>Remarks

Заменяет существующее значение *элементом.* В отладке сборки произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

## <a name="catllistswapelements"></a><a name="swapelements"></a>CAtlList:SwapElements

Вызовите этот метод для замены элементов в списке.

```cpp
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>Параметры

*pos1*<br/>
Первое значение POSITION.

*pos2*<br/>
Второе значение POSITION.

### <a name="remarks"></a>Remarks

Свопы элементов на двух указанных позициях. В отладочных сборках произойдет сбой утверждения, если значение позиции равно нулю.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CList](../../mfc/reference/clist-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
