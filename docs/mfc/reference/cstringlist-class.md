---
title: Класс CStringList
ms.date: 11/04/2016
f1_keywords:
- CStringList
- AFXCOLL/CStringList
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
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
ms.openlocfilehash: 08e481f010be688fb0b9c219caa1954c9960846f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346265"
---
# <a name="cstringlist-class"></a>Класс CStringList

Поддерживает списки объектов `CString` .

## <a name="syntax"></a>Синтаксис

```
class CStringList : public CObject
```

## <a name="members"></a>Участники

Функции-члены `CStringList` похожи на функции-члены класса [CObList](../../mfc/reference/coblist-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObList`. Если вы видите `CObject` указатель как возвращаемое значение, замените `CString` (не `CString` указатель). Если вы видите `CObject` указатель как параметр функции, замените `LPCTSTR`.

`CObject*& CObList::GetHead() const;`

, например, преобразуется в

`CString& CStringList::GetHead() const;`

и

`POSITION AddHead( CObject* <newElement> );`

преобразуется в

`POSITION AddHead( LPCTSTR <newElement> );`

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Создается пустой список.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Добавляет элемент (или все элементы из другого списка) в начало списка (делает нового заголовка).|
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Добавляет в конец списка (делает новый tail) элемента (или все элементы из другого списка).|
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|Получает положение элемента, определяемого значением указателя.|
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Получает положение, определяемое отсчитываемый от нуля индекс элемента.|
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Получает элемент в заданной позиции.|
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Возвращает количество элементов в этом списке.|
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Возвращает позицию головной элемент списка.|
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Получает следующий элемент для выполнения итерации.|
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Возвращает предыдущий элемент для выполнения итерации.|
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Возвращает количество элементов в этом списке.|
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|Возвращает заключительный фрагмент элемент списка (не может быть пустым).|
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Возвращает позицию заключительного элемента списка.|
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Вставляет новый элемент после заданной позиции.|
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Вставляет новый элемент до заданной позиции.|
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Проверяет условие пустой список (нет элементов).|
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Удаляет все элементы из этого списка.|
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Удаляет элемент из этого списка, указанного параметром position.|
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Удаляет элемент из головы списка.|
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Удаляет элемент из конца списка.|
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Задает элемент в заданной позиции.|

## <a name="remarks"></a>Примечания

Все сравнения выполняются по значению, это означает, что вместо адреса строки сравниваются символы в строке.

`CStringList` включает в себя IMPLEMENT_SERIAL-макрос для поддержки сериализации и записи элементов в дамп. Если список `CString` объекты хранятся в архив с помощью перегруженного оператора вставки или `Serialize` функция-член, чтобы каждый `CString` элемент сериализуется в свою очередь.

Если вам требуется дамп отдельных `CString` элементов, необходимо задать глубины контекста дампа 1 или более поздней версии.

Дополнительные сведения об использовании `CStringList`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CStringList`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
