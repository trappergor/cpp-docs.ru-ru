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
ms.openlocfilehash: 9e657bbf375a8babf1c03cc7254310956131d62b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449376"
---
# <a name="catllist-class"></a>Класс CAtlList

Этот класс предоставляет методы для создания и управления объект списка.

## <a name="syntax"></a>Синтаксис

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

#### <a name="parameters"></a>Параметры

*E*<br/>
Тип элемента.

*ETraits*<br/>
Код, используемый для копирования или перемещения элементов. См. в разделе [класс CElementTraits](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAtlList::INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlList::CAtlList](#catllist)|Конструктор.|
|[CAtlList:: ~ CAtlList](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlList::AddHead](#addhead)|Вызовите этот метод, чтобы добавить элемент в начало списка.|
|[CAtlList::AddHeadList](#addheadlist)|Этот метод используется для добавления существующего списка в начало списка.|
|[CAtlList::AddTail](#addtail)|Вызовите этот метод, чтобы добавить элемент в конец этого списка.|
|[CAtlList::AddTailList](#addtaillist)|Этот метод используется для добавления существующего списка в конец этого списка.|
|[CAtlList::AssertValid](#assertvalid)|Вызовите этот метод, чтобы убедиться, что он действителен.|
|[CAtlList::Find](#find)|Этот метод используется для поиска в списке для указанного элемента.|
|[CAtlList::FindIndex](#findindex)|Этот метод используется для получения позиции элемента, заданного значением индекса.|
|[CAtlList::GetAt](#getat)|Этот метод используется для возвращения элемента в указанной позиции в списке.|
|[CAtlList::GetCount](#getcount)|Этот метод используется для возврата количества объектов в списке.|
|[CAtlList::GetHead](#gethead)|Этот метод используется для возвращения элемента в начало списка.|
|[CAtlList::GetHeadPosition](#getheadposition)|Этот метод используется для получения позиции в начало списка.|
|[CAtlList::GetNext](#getnext)|Вызовите этот метод для возврата следующего элемента из списка.|
|[CAtlList::GetPrev](#getprev)|Вызовите этот метод для возврата предыдущего элемента в списке.|
|[CAtlList::GetTail](#gettail)|Этот метод используется для возвращения элемента в конец списка.|
|[CAtlList::GetTailPosition](#gettailposition)|Этот метод используется для получения позиции в конец списка.|
|[CAtlList::InsertAfter](#insertafter)|Этот метод используется для вставки нового элемента в списке после заданной позиции.|
|[CAtlList::InsertBefore](#insertbefore)|Этот метод используется для вставки нового элемента в списке перед указанным положением.|
|[CAtlList::IsEmpty](#isempty)|Этот метод используется для определения того, если список пуст.|
|[CAtlList::MoveToHead](#movetohead)|Вызовите этот метод, чтобы переместить элемент в начало списка.|
|[CAtlList::MoveToTail](#movetotail)|Вызовите этот метод, чтобы переместить элемент в конец списка.|
|[CAtlList::RemoveAll](#removeall)|Вызовите этот метод, чтобы удалить все элементы из списка.|
|[CAtlList::RemoveAt](#removeat)|Вызовите этот метод, чтобы удалить один элемент из списка.|
|[CAtlList::RemoveHead](#removehead)|Вызовите этот метод, чтобы удалить элемент в начало списка.|
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Вызовите этот метод, чтобы удалить элемент в начало списка, не возвращая значения.|
|[CAtlList::RemoveTail](#removetail)|Вызовите этот метод, чтобы удалить элемент в конец списка.|
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Вызовите этот метод, чтобы удалить элемент в конец списка, не возвращая значения.|
|[CAtlList::SetAt](#setat)|Этот метод используется для задания значения элемента в заданной позиции в списке.|
|[CAtlList::SwapElements](#swapelements)|Вызовите этот метод для замены элементов в списке.|

## <a name="remarks"></a>Примечания

`CAtlList` Поддерживает упорядоченные списки неуникальных объектов, доступные последовательно или по значению класс. `CAtlList` списки ведут себя как двунаправленный список. Каждый список содержит head и хвост и новые элементы (или списки в некоторых случаях) можно добавлять в любой конец списка, или вставляться до или после определенных элементов.

Большая часть `CAtlList` методов использовать значения позиции. Это значение используется методами для ссылки на расположение фактический объем памяти, где элементы хранятся и не рассчитываются и прогнозируемые напрямую. Если это необходимо, чтобы получить доступ к *n*й элемент в списке, а метод [CAtlList::FindIndex](#findindex) возвращает соответствующее значение для указанного индекса позиции. Методы [CAtlList::GetNext](#getnext) и [CAtlList::GetPrev](#getprev) может использоваться для перебора объектов в списке.

Дополнительные сведения о классов коллекций, доступных с библиотекой ATL, см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="addhead"></a>  CAtlList::AddHead

Вызовите этот метод, чтобы добавить элемент в начало списка.

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Новый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию вновь добавленного элемента.

### <a name="remarks"></a>Примечания

Если используется первая версия, пустой элемент будет создан с помощью его конструктора по умолчанию, а не его конструктор копии.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

##  <a name="addheadlist"></a>  CAtlList::AddHeadList

Этот метод используется для добавления существующего списка в начало списка.

```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Параметры

*plNew*<br/>
Список для добавления.

### <a name="remarks"></a>Примечания

Список указываемых *plNew* вставляется в начале существующего списка. В отладочных сборках, произойдет сбой утверждения, если *plNew* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

##  <a name="addtail"></a>  CAtlList::AddTail

Вызовите этот метод, чтобы добавить элемент в конец этого списка.

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Добавляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ПОЗИЦИЮ вновь добавленного элемента.

### <a name="remarks"></a>Примечания

Если используется первая версия, пустой элемент будет создан с помощью его конструктора по умолчанию, а не его конструктор копии. Элемент добавлен в конец списка, и поэтому теперь она становится заключительный фрагмент. Этот метод может использоваться с пустым списком.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

##  <a name="addtaillist"></a>  CAtlList::AddTailList

Этот метод используется для добавления существующего списка в конец этого списка.

```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Параметры

*plNew*<br/>
Список для добавления.

### <a name="remarks"></a>Примечания

Список указываемых *plNew* вставляется после последнего элемента (если таковые имеются) в объекте списка. Последним элементом в *plNew* список становится таким образом заключительный фрагмент. В отладочных сборках, произойдет сбой утверждения, если *plNew* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

##  <a name="assertvalid"></a>  CAtlList::AssertValid

Вызовите этот метод, чтобы убедиться, что он действителен.

```
void AssertValid() const;
```

### <a name="remarks"></a>Примечания

В отладочных сборках произойдет сбой утверждения, если объект-список не является допустимым. Был допустимым, должен иметь пустой список, head и tail, которые указывают на значение NULL, и должен иметь список, который не является пустым, head и tail, указывающий на допустимые адреса.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

##  <a name="catllist"></a>  CAtlList::CAtlList

Конструктор.

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

Конструктор `CAtlList` объекта. Размер блока — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

##  <a name="dtor"></a>  CAtlList:: ~ CAtlList

Деструктор

```
~CAtlList() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы, включая вызов [CAtlList::RemoveAll](#removeall) для удаления всех элементов из списка.

В отладочных сборках, произойдет сбой утверждения, если список по-прежнему содержит некоторые элементы после вызова `RemoveAll`.

##  <a name="find"></a>  CAtlList::Find

Этот метод используется для поиска в списке для указанного элемента.

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>Параметры

*Элемент*<br/>
Элемент, который требуется найти в списке.

*posStartAfter*<br/>
Начальное положение для поиска. Если значение не указано, поиск начинается с головным элементом.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение ПОЗИЦИИ элемента, если найдено, в противном случае возвращается значение NULL.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет сбой утверждения, если объект-список не является допустимым или *posStartAfter* значение выходит за пределы диапазона.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

##  <a name="findindex"></a>  CAtlList::FindIndex

Этот метод используется для получения позиции элемента, заданного значением индекса.

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>Параметры

*iElement*<br/>
Отсчитываемый от нуля индекс элемента списка требуется.

### <a name="return-value"></a>Возвращаемое значение

Возвращает соответствующий значение ПОЗИЦИИ, или значение NULL, если *iElement* выходит за пределы диапазона.

### <a name="remarks"></a>Примечания

Этот метод возвращает ПОЗИЦИЮ, соответствующее значению заданного индекса, предоставляя доступ к *n*й элемент в списке.

В отладочных сборках произойдет сбой утверждения, если объект-список не является допустимым.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

##  <a name="getat"></a>  CAtlList::GetAt

Этот метод используется для возвращения элемента в указанной позиции в списке.

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
ПОЗИЦИЯ значение, указывающее конкретный элемент.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на или копии элемента.

### <a name="remarks"></a>Примечания

Если список **const**, `GetAt` возвращает копию элемента. Это позволяет вызвать метод для использования только в правой части оператора присваивания и защищает списка от изменения.

Если список не является **const**, `GetAt` возвращает ссылку на элемент. Это позволяет вызвать метод для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

См. в примере [CAtlList::FindIndex](#findindex).

##  <a name="getcount"></a>  CAtlList::GetCount

Этот метод используется для возврата количества объектов в списке.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в списке.

### <a name="example"></a>Пример

См. в примере [CAtlList::Find](#find).

##  <a name="gethead"></a>  CAtlList::GetHead

Этот метод используется для возвращения элемента в начало списка.

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на или копии элемента, в начало списка.

### <a name="remarks"></a>Примечания

Если список **const**, `GetHead` возвращает копию объекта элемент в начало списка. Это позволяет вызвать метод для использования только в правой части оператора присваивания и защищает списка от изменения.

Если список не является **const**, `GetHead` возвращает ссылку на элемент в начало списка. Это позволяет вызвать метод для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

В отладочных сборках произойдет сбой утверждения, если заголовок списка указывает на значение NULL.

### <a name="example"></a>Пример

См. в примере [CAtlList::AddHead](#addhead).

##  <a name="getheadposition"></a>  CAtlList::GetHeadPosition

Этот метод используется для получения позиции в начало списка.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение ПОЗИЦИИ, соответствующий элемент в начало списка.

### <a name="remarks"></a>Примечания

Если список пуст, возвращаемое значение равно NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

##  <a name="getnext"></a>  CAtlList::GetNext

Вызовите этот метод для возврата следующего элемента из списка.

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение ПОЗИЦИИ, возвращенный предыдущим вызовом `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), или других `CAtlList` метод.

### <a name="return-value"></a>Возвращаемое значение

Если список **const**, `GetNext` возвращает копию объекта следующему элементу списка. Это позволяет вызвать метод для использования только в правой части оператора присваивания и защищает списка от изменения.

Если список не является **const**, `GetNext` возвращает ссылку к следующему элементу списка. Это позволяет вызвать метод для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Счетчик ПОЗИЦИИ, *pos*, к следующему элементу в списке, или значение NULL, если никакие элементы не обновляется. В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

См. в примере [CAtlList::GetHeadPosition](#getheadposition).

##  <a name="getprev"></a>  CAtlList::GetPrev

Вызовите этот метод для возврата предыдущего элемента в списке.

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение ПОЗИЦИИ, возвращенный предыдущим вызовом `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), или других `CAtlList` метод.

### <a name="return-value"></a>Возвращаемое значение

Если список **const**, `GetPrev` возвращает копию объекта элемента списка. Это позволяет вызвать метод для использования только в правой части оператора присваивания и защищает списка от изменения.

Если список не является **const**, `GetPrev` возвращает ссылку на элемент списка. Это позволяет вызвать метод для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Счетчик ПОЗИЦИИ, *pos*, обновляется до предыдущего элемента в списке, или значение NULL, если отсутствуют дополнительные элементы. В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

См. в примере [CAtlList::GetTailPosition](#gettailposition).

##  <a name="gettail"></a>  CAtlList::GetTail

Этот метод используется для возвращения элемента в конец списка.

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на или копию, элемент в конец списка.

### <a name="remarks"></a>Примечания

Если список **const**, `GetTail` возвращает копию объекта элемент в начало списка. Это позволяет вызвать метод для использования только в правой части оператора присваивания и защищает списка от изменения.

Если список не является **const**, `GetTail` возвращает ссылку на элемент в начало списка. Это позволяет вызвать метод для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

В отладочных сборках произойдет сбой утверждения, если хвост списка указывает на значение NULL.

### <a name="example"></a>Пример

См. в примере [CAtlList::AddTail](#addtail).

##  <a name="gettailposition"></a>  CAtlList::GetTailPosition

Этот метод используется для получения позиции в конец списка.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение ПОЗИЦИИ, соответствующий элемент в конец списка.

### <a name="remarks"></a>Примечания

Если список пуст, возвращаемое значение равно NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

##  <a name="inargtype"></a>  CAtlList::INARGTYPE

Тип, используемый, когда элемент передается в качестве входного аргумента.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertafter"></a>  CAtlList::InsertAfter

Этот метод используется для вставки нового элемента в списке после заданной позиции.

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение ПОЗИЦИИ, после чего будет вставлен новый элемент.

*Элемент*<br/>
Вставляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение ПОЗИЦИИ нового элемента.

### <a name="remarks"></a>Примечания

В отладочных сборках Сбой утверждения произойдет, если список не является допустимым, если вставка завершается ошибкой, или в том случае, если предпринята попытка вставить элемент после заключительный фрагмент.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

##  <a name="insertbefore"></a>  CAtlList::InsertBefore

Этот метод используется для вставки нового элемента в списке перед указанным положением.

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
В списке перед этой ПОЗИЦИИ значение будет вставлен новый элемент.

*Элемент*<br/>
Вставляемый элемент.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение ПОЗИЦИИ нового элемента.

### <a name="remarks"></a>Примечания

В отладочных сборках Сбой утверждения произойдет, если список не является допустимым, если вставка завершается ошибкой, или в том случае, если предпринята попытка вставить элемент перед заголовок.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

##  <a name="isempty"></a>  CAtlList::IsEmpty

Этот метод используется для определения того, если список пуст.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если список не содержит объектов, в противном случае — значение false.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

##  <a name="movetohead"></a>  CAtlList::MoveToHead

Вызовите этот метод, чтобы переместить элемент в начало списка.

```
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение ПОЗИЦИИ элемента, который требуется переместить.

### <a name="remarks"></a>Примечания

Указанный элемент перемещается из ее текущей позиции в начало списка. В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

##  <a name="movetotail"></a>  CAtlList::MoveToTail

Вызовите этот метод, чтобы переместить элемент в конец списка.

```
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение ПОЗИЦИИ элемента, который требуется переместить.

### <a name="remarks"></a>Примечания

Указанный элемент перемещается из ее текущей позиции в конец списка. В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

См. в примере [CAtlList::MoveToHead](#movetohead).

##  <a name="removeall"></a>  CAtlList::RemoveAll

Вызовите этот метод, чтобы удалить все элементы из списка.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Примечания

Этот метод удаляет все элементы из списка и освобождает выделенную память. В сборках отлаживает ATLASSERT возникает, если все элементы не будут удалены или оказались поврежденными структуры списка.

### <a name="example"></a>Пример

См. в примере [CAtlList::IsEmpty](#isempty).

##  <a name="removeat"></a>  CAtlList::RemoveAt

Вызовите этот метод, чтобы удалить один элемент из списка.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение ПОЗИЦИИ элемента, который требуется удалить.

### <a name="remarks"></a>Примечания

Элемент, который ссылается *pos* удаляется, и память освобождается. Это допустимо использовать `RemoveAt` удаляемый головным элементом или хвост списка.

В отладочных сборках произойдет сбой утверждения, если список не является допустимым или удаление элемента ведет список доступ к памяти, который не является частью структуры списка.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

##  <a name="removehead"></a>  CAtlList::RemoveHead

Вызовите этот метод, чтобы удалить элемент в начало списка.

```
E RemoveHead();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент в начало списка.

### <a name="remarks"></a>Примечания

Головной элемент удаляется из списка, а память освобождается. Возвращает копию элемента. В отладочных сборках произойдет сбой утверждения, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

##  <a name="removeheadnoreturn"></a>  CAtlList::RemoveHeadNoReturn

Вызовите этот метод, чтобы удалить элемент в начало списка, не возвращая значения.

```
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>Примечания

Головной элемент удаляется из списка, а память освобождается. В отладочных сборках произойдет сбой утверждения, если список пуст.

### <a name="example"></a>Пример

См. в примере [CAtlList::IsEmpty](#isempty).

##  <a name="removetail"></a>  CAtlList::RemoveTail

Вызовите этот метод, чтобы удалить элемент в конец списка.

```
E RemoveTail();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент в конец списка.

### <a name="remarks"></a>Примечания

Заключительный фрагмент элемент удаляется из списка, а память освобождается. Возвращает копию элемента. В отладочных сборках произойдет сбой утверждения, если список пуст.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

##  <a name="removetailnoreturn"></a>  CAtlList::RemoveTailNoReturn

Вызовите этот метод, чтобы удалить элемент в конец списка, не возвращая значения.

```
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>Примечания

Заключительный фрагмент элемент удаляется из списка, а память освобождается. В отладочных сборках произойдет сбой утверждения, если список пуст.

### <a name="example"></a>Пример

См. в примере [CAtlList::IsEmpty](#isempty).

##  <a name="setat"></a>  CAtlList::SetAt

Этот метод используется для задания значения элемента в заданной позиции в списке.

```
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Значение положение, соответствующее элемента, который требуется изменить.

*Элемент*<br/>
Новое значение элемента.

### <a name="remarks"></a>Примечания

Заменяет существующее значение *элемент*. В отладочных сборках, произойдет сбой утверждения, если *pos* равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

##  <a name="swapelements"></a>  CAtlList::SwapElements

Вызовите этот метод для замены элементов в списке.

```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>Параметры

*pos1*<br/>
Первое значение ПОЗИЦИИ.

*pos2*<br/>
Второе значение ПОЗИЦИИ.

### <a name="remarks"></a>Примечания

Меняет местами элементы в двух местах, указан. В отладочных сборках Сбой утверждения произойдет, если одно из значений позиции равен NULL.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>См. также

[Класс CList](../../mfc/reference/clist-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
