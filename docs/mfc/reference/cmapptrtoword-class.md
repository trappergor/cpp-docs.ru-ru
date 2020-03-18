---
title: Класс Кмапптртоворд
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToWord
- AFXCOLL/CMapPtrToWord
- AFXCOLL/CMapPtrToWord::CMapPtrToWord
- AFXCOLL/CMapPtrToWord::GetCount
- AFXCOLL/CMapPtrToWord::GetHashTableSize
- AFXCOLL/CMapPtrToWord::GetNextAssoc
- AFXCOLL/CMapPtrToWord::GetSize
- AFXCOLL/CMapPtrToWord::GetStartPosition
- AFXCOLL/CMapPtrToWord::HashKey
- AFXCOLL/CMapPtrToWord::InitHashTable
- AFXCOLL/CMapPtrToWord::IsEmpty
- AFXCOLL/CMapPtrToWord::Lookup
- AFXCOLL/CMapPtrToWord::LookupKey
- AFXCOLL/CMapPtrToWord::RemoveAll
- AFXCOLL/CMapPtrToWord::RemoveKey
- AFXCOLL/CMapPtrToWord::SetAt
helpviewer_keywords:
- CMapPtrToWord [MFC], CMapPtrToWord
- CMapPtrToWord [MFC], GetCount
- CMapPtrToWord [MFC], GetHashTableSize
- CMapPtrToWord [MFC], GetNextAssoc
- CMapPtrToWord [MFC], GetSize
- CMapPtrToWord [MFC], GetStartPosition
- CMapPtrToWord [MFC], HashKey
- CMapPtrToWord [MFC], InitHashTable
- CMapPtrToWord [MFC], IsEmpty
- CMapPtrToWord [MFC], Lookup
- CMapPtrToWord [MFC], LookupKey
- CMapPtrToWord [MFC], RemoveAll
- CMapPtrToWord [MFC], RemoveKey
- CMapPtrToWord [MFC], SetAt
ms.assetid: 4631c6b6-d49f-49d9-adc0-1e0491e32d7b
ms.openlocfilehash: 698e306896fd62888a84b6d6ce55fb4c9678187b
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442655"
---
# <a name="cmapptrtoword-class"></a>Класс Кмапптртоворд

Поддерживает сопоставления 16-разрядных ключевых слов пустыми указателями.

## <a name="syntax"></a>Синтаксис

```
class CMapPtrToWord : public CObject
```

## <a name="members"></a>Члены

Функции элементов `CMapPtrToWord` похожи на функции членов класса [кмапстрингтуб](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Когда вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, замените слово. Когда вы видите `CString` или указатель **const** на **char** в качестве параметра функции или возвращаемого значения, замените указатель на **void**.

`BOOL CMapPtrToWord::Lookup( const void* <key>, WORD& <rValue> ) const;`

, например, преобразуется в

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кмапптртоворд:: Кмапптртоворд](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кмапптртоворд:: NOCOUNT](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает число элементов в этой карте.|
|[Кмапптртоворд:: Жесаштаблесизе](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|
|[Кмапптртоворд:: Жетнекстассок](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Возвращает следующий элемент для итерации.|
|[Кмапптртоворд:: DataSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает число элементов в этой карте.|
|[Кмапптртоворд:: Жетстартпоситион](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает расположение первого элемента.|
|[Кмапптртоворд:: Хашкэй](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[Кмапптртоворд:: Инисаштабле](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицу.|
|[Кмапптртоворд:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие на пустую карту (нет элементов).|
|[Кмапптртоворд:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указателя void. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[Кмапптртоворд:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Кмапптртоворд:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой схемы.|
|[Кмапптртоворд:: Ремовекэй](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный ключом.|
|[Кмапптртоворд:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в карту; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Кмапптртоворд:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в Map — подстановку оператора для `SetAt`.|

## <a name="remarks"></a>Remarks

`CMapWordToPtr` включает макрос IMPLEMENT_DYNAMIC для поддержки доступа к типу во время выполнения и дампа в объект `CDumpContext`. Если требуется дамп отдельных элементов Map, необходимо установить глубину контекста дампа в 1 или более.

Карты указателей на слово не могут быть сериализованы.

При удалении объекта `CMapPtrToWord` или удалении его элементов указатели и слова удаляются. Сущности, на которые ссылаются указатели ключей, не удаляются.

Дополнительные сведения о `CMapPtrToWord`см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToWord`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
