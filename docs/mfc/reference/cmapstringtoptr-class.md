---
title: Класс Кмапстрингтоптр
ms.date: 11/04/2016
f1_keywords:
- CMapStringToPtr
- AFXCOLL/CMapStringToPtr
- AFXCOLL/CMapStringToPtr::CMapStringToPtr
- AFXCOLL/CMapStringToPtr::GetCount
- AFXCOLL/CMapStringToPtr::GetHashTableSize
- AFXCOLL/CMapStringToPtr::GetNextAssoc
- AFXCOLL/CMapStringToPtr::GetSize
- AFXCOLL/CMapStringToPtr::GetStartPosition
- AFXCOLL/CMapStringToPtr::HashKey
- AFXCOLL/CMapStringToPtr::InitHashTable
- AFXCOLL/CMapStringToPtr::IsEmpty
- AFXCOLL/CMapStringToPtr::Lookup
- AFXCOLL/CMapStringToPtr::LookupKey
- AFXCOLL/CMapStringToPtr::RemoveAll
- AFXCOLL/CMapStringToPtr::RemoveKey
- AFXCOLL/CMapStringToPtr::SetAt
helpviewer_keywords:
- CMapStringToPtr [MFC], CMapStringToPtr
- CMapStringToPtr [MFC], GetCount
- CMapStringToPtr [MFC], GetHashTableSize
- CMapStringToPtr [MFC], GetNextAssoc
- CMapStringToPtr [MFC], GetSize
- CMapStringToPtr [MFC], GetStartPosition
- CMapStringToPtr [MFC], HashKey
- CMapStringToPtr [MFC], InitHashTable
- CMapStringToPtr [MFC], IsEmpty
- CMapStringToPtr [MFC], Lookup
- CMapStringToPtr [MFC], LookupKey
- CMapStringToPtr [MFC], RemoveAll
- CMapStringToPtr [MFC], RemoveKey
- CMapStringToPtr [MFC], SetAt
ms.assetid: 1ac11143-eb0a-4511-a662-2df0d1d9005b
ms.openlocfilehash: 0e722b305dad6595eb67b1a235c375d21f674353
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442606"
---
# <a name="cmapstringtoptr-class"></a>Класс Кмапстрингтоптр

Поддерживает сопоставления пустых указателей, зашифрованных объектами `CString` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToPtr : public CObject
```

## <a name="members"></a>Члены

Функции элементов `CMapStringToPtr` похожи на функции членов класса [кмапстрингтуб](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Когда вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, замените указатель на **void**.

`BOOL CMapStringToPtr::Lookup( LPCTSTR <key>, void*& <rValue> ) const;`

, например, преобразуется в

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кмапстрингтоптр:: Кмапстрингтоптр](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кмапстрингтоптр:: NOCOUNT](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает число элементов в этой карте.|
|[Кмапстрингтоптр:: Жесаштаблесизе](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|
|[Кмапстрингтоптр:: Жетнекстассок](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Возвращает следующий элемент для итерации.|
|[Кмапстрингтоптр:: DataSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает число элементов в этой карте.|
|[Кмапстрингтоптр:: Жетстартпоситион](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает расположение первого элемента.|
|[Кмапстрингтоптр:: Хашкэй](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[Кмапстрингтоптр:: Инисаштабле](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицу.|
|[Кмапстрингтоптр:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие на пустую карту (нет элементов).|
|[Кмапстрингтоптр:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указателя void. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[Кмапстрингтоптр:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Кмапстрингтоптр:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой схемы.|
|[Кмапстрингтоптр:: Ремовекэй](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный ключом.|
|[Кмапстрингтоптр:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в карту; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Кмапстрингтоптр:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в Map — подстановку оператора для `SetAt`.|

## <a name="remarks"></a>Remarks

`CMapStringToPtr` включает макрос IMPLEMENT_DYNAMIC для поддержки доступа к типу во время выполнения и дампа в объект `CDumpContext`. Если требуется дамп отдельных элементов Map, необходимо установить глубину контекста дампа в 1 или более.

Карты типа "строка-указатель" не могут быть сериализованы.

При удалении объекта `CMapStringToPtr` или удалении его элементов удаляются `CString`ые объекты ключа и слова.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToPtr`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
