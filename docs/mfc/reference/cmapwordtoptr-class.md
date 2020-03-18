---
title: Класс Кмапвордтоптр
ms.date: 11/04/2016
f1_keywords:
- CMapWordToPtr
- AFXCOLL/CMapWordToPtr
- AFXCOLL/CMapWordToPtr::CMapWordToPtr
- AFXCOLL/CMapWordToPtr::GetCount
- AFXCOLL/CMapWordToPtr::GetHashTableSize
- AFXCOLL/CMapWordToPtr::GetNextAssoc
- AFXCOLL/CMapWordToPtr::GetSize
- AFXCOLL/CMapWordToPtr::GetStartPosition
- AFXCOLL/CMapWordToPtr::HashKey
- AFXCOLL/CMapWordToPtr::InitHashTable
- AFXCOLL/CMapWordToPtr::IsEmpty
- AFXCOLL/CMapWordToPtr::Lookup
- AFXCOLL/CMapWordToPtr::LookupKey
- AFXCOLL/CMapWordToPtr::RemoveAll
- AFXCOLL/CMapWordToPtr::RemoveKey
- AFXCOLL/CMapWordToPtr::SetAt
helpviewer_keywords:
- CMapWordToPtr [MFC], CMapWordToPtr
- CMapWordToPtr [MFC], GetCount
- CMapWordToPtr [MFC], GetHashTableSize
- CMapWordToPtr [MFC], GetNextAssoc
- CMapWordToPtr [MFC], GetSize
- CMapWordToPtr [MFC], GetStartPosition
- CMapWordToPtr [MFC], HashKey
- CMapWordToPtr [MFC], InitHashTable
- CMapWordToPtr [MFC], IsEmpty
- CMapWordToPtr [MFC], Lookup
- CMapWordToPtr [MFC], LookupKey
- CMapWordToPtr [MFC], RemoveAll
- CMapWordToPtr [MFC], RemoveKey
- CMapWordToPtr [MFC], SetAt
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
ms.openlocfilehash: 71d79f9f57be2cdfe16c526bd50173a8ec3c5829
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442574"
---
# <a name="cmapwordtoptr-class"></a>Класс Кмапвордтоптр

Поддерживает сопоставления пустым указателям, зашифрованным 16-разрядными ключевыми словами.

## <a name="syntax"></a>Синтаксис

```
class CMapWordToPtr : public CObject
```

## <a name="members"></a>Члены

Функции элементов `CMapWordToPtr` похожи на функции членов класса [кмапстрингтуб](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Когда вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, замените указатель на **void**. Когда вы видите `CString` или указатель **const** на **char** в качестве параметра функции или возвращаемого значения, замените слово.

`BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`

, например, преобразуется в

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кмапвордтоптр:: Кмапвордтоптр](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кмапвордтоптр:: NOCOUNT](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает число элементов в этой карте.|
|[Кмапвордтоптр:: Жесаштаблесизе](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|
|[Кмапвордтоптр:: Жетнекстассок](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Возвращает следующий элемент для итерации.|
|[Кмапвордтоптр:: DataSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает число элементов в этой карте.|
|[Кмапвордтоптр:: Жетстартпоситион](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает расположение первого элемента.|
|[Кмапвордтоптр:: Хашкэй](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[Кмапвордтоптр:: Инисаштабле](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицу.|
|[Кмапвордтоптр:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие на пустую карту (нет элементов).|
|[Кмапвордтоптр:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указателя void. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[Кмапвордтоптр:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Кмапвордтоптр:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой схемы.|
|[Кмапвордтоптр:: Ремовекэй](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный ключом.|
|[Кмапвордтоптр:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в карту; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Кмапвордтоптр:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в Map — подстановку оператора для `SetAt`.|

## <a name="remarks"></a>Remarks

`CMapWordToPtr` включает макрос IMPLEMENT_DYNAMIC для поддержки доступа к типу во время выполнения и дампа в объект `CDumpContext`. Если требуется дамп отдельных элементов Map, необходимо установить глубину контекста дампа в 1 или более.

Карты с указателями на слова не могут быть сериализованы.

При удалении объекта `CMapWordToPtr` или удалении его элементов происходит удаление слов и указателей. Сущности, на которые ссылаются указатели, не удаляются.

Дополнительные сведения о `CMapWordToPtr`см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapWordToPtr`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
