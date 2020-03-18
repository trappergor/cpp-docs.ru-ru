---
title: Класс Куинтаррай
ms.date: 11/04/2016
f1_keywords:
- CUIntArray
- AFXCOLL/CUIntArray
- AFXCOLL/CUIntArray::CUIntArray
- AFXCOLL/CUIntArray::Add
- AFXCOLL/CUIntArray::Append
- AFXCOLL/CUIntArray::Copy
- AFXCOLL/CUIntArray::ElementAt
- AFXCOLL/CUIntArray::FreeExtra
- AFXCOLL/CUIntArray::GetAt
- AFXCOLL/CUIntArray::GetCount
- AFXCOLL/CUIntArray::GetData
- AFXCOLL/CUIntArray::GetSize
- AFXCOLL/CUIntArray::GetUpperBound
- AFXCOLL/CUIntArray::InsertAt
- AFXCOLL/CUIntArray::IsEmpty
- AFXCOLL/CUIntArray::RemoveAll
- AFXCOLL/CUIntArray::RemoveAt
- AFXCOLL/CUIntArray::SetAt
- AFXCOLL/CUIntArray::SetAtGrow
- AFXCOLL/CUIntArray::SetSize
helpviewer_keywords:
- CUIntArray [MFC], CUIntArray
- CUIntArray [MFC], Add
- CUIntArray [MFC], Append
- CUIntArray [MFC], Copy
- CUIntArray [MFC], ElementAt
- CUIntArray [MFC], FreeExtra
- CUIntArray [MFC], GetAt
- CUIntArray [MFC], GetCount
- CUIntArray [MFC], GetData
- CUIntArray [MFC], GetSize
- CUIntArray [MFC], GetUpperBound
- CUIntArray [MFC], InsertAt
- CUIntArray [MFC], IsEmpty
- CUIntArray [MFC], RemoveAll
- CUIntArray [MFC], RemoveAt
- CUIntArray [MFC], SetAt
- CUIntArray [MFC], SetAtGrow
- CUIntArray [MFC], SetSize
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
ms.openlocfilehash: 932062ec289a34cffcd929853233a0c7c81a7a72
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447537"
---
# <a name="cuintarray-class"></a>Класс Куинтаррай

Поддерживает массивы целых чисел без знака.

## <a name="syntax"></a>Синтаксис

```
class CUIntArray : public CObject
```

## <a name="members"></a>Члены

Функции элементов `CUIntArray` похожи на функции членов класса [кобаррай](../../mfc/reference/cobarray-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CObArray`. Когда вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, замените UINT.

`CObject* CObArray::GetAt( int <nIndex> ) const;`

, например, преобразуется в

`UINT CUIntArray::GetAt( int <nIndex> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Куинтаррай:: Куинтаррай](../../mfc/reference/cobarray-class.md#cobarray)|Создает пустой массив.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Куинтаррай:: Add](../../mfc/reference/cobarray-class.md#add)|Добавляет элемент в конец массива. При необходимости размер массива увеличивается.|
|[Куинтаррай:: Append](../../mfc/reference/cobarray-class.md#append)|Добавляет другой массив к массиву. При необходимости размер массива увеличивается.|
|[Куинтаррай:: Copy](../../mfc/reference/cobarray-class.md#copy)|Копирует другой массив в этот массив. При необходимости размер массива увеличивается.|
|[Куинтаррай:: ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Возвращает временную ссылку на указатель элемента в массиве.|
|[Куинтаррай:: Фриекстра](../../mfc/reference/cobarray-class.md#freeextra)|Освобождает всю неиспользуемую память сверх текущей верхней границы.|
|[Куинтаррай:: GetAt](../../mfc/reference/cobarray-class.md#getat)|Возвращает значение по указанному индексу.|
|[Куинтаррай:: NOCOUNT](../../mfc/reference/cobarray-class.md#getcount)|Возвращает количество элементов в массиве.|
|[Куинтаррай:: GetData](../../mfc/reference/cobarray-class.md#getdata)|Разрешает доступ к элементам в массиве. Может иметь значение NULL.|
|[Куинтаррай:: DataSize](../../mfc/reference/cobarray-class.md#getsize)|Возвращает количество элементов в массиве.|
|[Куинтаррай:: GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|Возвращает самый большой допустимый индекс.|
|[Куинтаррай:: Инсертат](../../mfc/reference/cobarray-class.md#insertat)|Вставляет элемент (или все элементы в другом массиве) по указанному индексу.|
|[Куинтаррай:: IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Определяет, пуст ли массив.|
|[Куинтаррай:: RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Удаляет все элементы из этого массива.|
|[Куинтаррай:: RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Удаляет элемент по указанному индексу.|
|[Куинтаррай:: SetAt](../../mfc/reference/cobarray-class.md#setat)|Задает значение для указанного индекса. Размер массива не увеличивается.|
|[Куинтаррай:: Сетатгров](../../mfc/reference/cobarray-class.md#setatgrow)|Задает значение для указанного индекса. При необходимости размер массива увеличивается.|
|[Куинтаррай:: SetSize](../../mfc/reference/cobarray-class.md#setsize)|Задает число элементов, которые будут храниться в этом массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Куинтаррай:: operator \[ \]](../../mfc/reference/cobarray-class.md#operator_at)|Получает или задает элемент с указанным индексом.|

## <a name="remarks"></a>Remarks

Целое число без знака или UINT отличается от слов и даублевордс в том, что физический размер UINT может изменяться в зависимости от целевой операционной среды. Значение UINT имеет тот же размер, что и даублеворд.

`CUIntArray` включает макрос [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) для поддержки доступа к типам времени выполнения и дампа в объекте [CDumpContext](../../mfc/reference/cdumpcontext-class.md) . Если требуется дамп отдельных беззнаковых целых элементов, необходимо задать для контекста дампа значение 1 или больше. Целочисленные массивы без знака не могут быть сериализованы.

> [!NOTE]
>  Перед работой с массивом используйте функцию `SetSize`, чтобы определить его размер и выделить под него память. Если не использовать функцию `SetSize`, при добавлении элементов в массив он будет часто копироваться и для него снова и снова будет повторно выделяться память. Это может привести к ухудшению производительности и фрагментации памяти.

Дополнительные сведения об использовании `CUIntArray`см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CUIntArray`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
