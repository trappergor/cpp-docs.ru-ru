---
title: Класс Кмапптртоптр
ms.date: 11/04/2016
f1_keywords:
- CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr::CMapPtrToPtr
- AFXCOLL/CMapPtrToPtr::GetCount
- AFXCOLL/CMapPtrToPtr::GetHashTableSize
- AFXCOLL/CMapPtrToPtr::GetNextAssoc
- AFXCOLL/CMapPtrToPtr::GetSize
- AFXCOLL/CMapPtrToPtr::GetStartPosition
- AFXCOLL/CMapPtrToPtr::HashKey
- AFXCOLL/CMapPtrToPtr::InitHashTable
- AFXCOLL/CMapPtrToPtr::IsEmpty
- AFXCOLL/CMapPtrToPtr::Lookup
- AFXCOLL/CMapPtrToPtr::LookupKey
- AFXCOLL/CMapPtrToPtr::RemoveAll
- AFXCOLL/CMapPtrToPtr::RemoveKey
- AFXCOLL/CMapPtrToPtr::SetAt
helpviewer_keywords:
- CMapPtrToPtr [MFC], CMapPtrToPtr
- CMapPtrToPtr [MFC], GetCount
- CMapPtrToPtr [MFC], GetHashTableSize
- CMapPtrToPtr [MFC], GetNextAssoc
- CMapPtrToPtr [MFC], GetSize
- CMapPtrToPtr [MFC], GetStartPosition
- CMapPtrToPtr [MFC], HashKey
- CMapPtrToPtr [MFC], InitHashTable
- CMapPtrToPtr [MFC], IsEmpty
- CMapPtrToPtr [MFC], Lookup
- CMapPtrToPtr [MFC], LookupKey
- CMapPtrToPtr [MFC], RemoveAll
- CMapPtrToPtr [MFC], RemoveKey
- CMapPtrToPtr [MFC], SetAt
ms.assetid: 23cbbaec-9d64-48f2-92ae-5e24fa64b926
ms.openlocfilehash: b4ae511caab8278daf723bbcb8ffc5d57f5a1cd0
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442672"
---
# <a name="cmapptrtoptr-class"></a>Класс Кмапптртоптр

Поддерживает сопоставления пустых указателей, зашифрованных пустыми указателями.

## <a name="syntax"></a>Синтаксис

```
class CMapPtrToPtr : public CObject
```

## <a name="members"></a>Члены

Функции элементов `CMapPtrToPtr` похожи на функции членов класса [кмапстрингтуб](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Когда вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, замените указатель на **void**. Когда вы видите `CString` или указатель **const** на **char** в качестве параметра функции или возвращаемого значения, замените указатель на **void**.

`BOOL CMapPtrToPtr::Lookup( void* <key>, void*& <rValue> ) const;`

, например, преобразуется в

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кмапптртоптр:: Кмапптртоптр](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кмапптртоптр:: NOCOUNT](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает число элементов в этой карте.|
|[Кмапптртоптр:: Жесаштаблесизе](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|
|[Кмапптртоптр:: Жетнекстассок](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Возвращает следующий элемент для итерации.|
|[Кмапптртоптр:: DataSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает число элементов в этой карте.|
|[Кмапптртоптр:: Жетстартпоситион](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает расположение первого элемента.|
|[Кмапптртоптр:: Хашкэй](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[Кмапптртоптр:: Инисаштабле](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицу.|
|[Кмапптртоптр:: IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие на пустую карту (нет элементов).|
|[Кмапптртоптр:: Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указателя void. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[Кмапптртоптр:: LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Кмапптртоптр:: RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из этой схемы.|
|[Кмапптртоптр:: Ремовекэй](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный ключом.|
|[Кмапптртоптр:: SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в карту; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Кмапптртоптр:: operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в Map — подстановку оператора для `SetAt`.|

## <a name="remarks"></a>Remarks

`CMapPtrToPtr` включает макрос IMPLEMENT_DYNAMIC для поддержки доступа к типу во время выполнения и дампа в объект `CDumpContext`. Если требуется дамп отдельных элементов карт (значений указателей), необходимо задать для контекста дампа значение 1 или больше.

Карты указателей на указатели не могут быть сериализованы.

При удалении объекта `CMapPtrToPtr` или удалении его элементов удаляются только указатели, а не сущности, на которые они ссылаются.

Дополнительные сведения о `CMapPtrToPtr`см. в статье [коллекции](../../mfc/collections.md)статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapPtrToPtr`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
