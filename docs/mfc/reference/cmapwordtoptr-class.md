---
title: Класс CMapWordToPtr
ms.date: 11/04/2016
f1_keywords:
- CMapWordToPtr
- AFXCOLL/CMapWordToPtr
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
ms.openlocfilehash: 5df8d9e853d934d8c83398cc266c6f49634fa9e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605144"
---
# <a name="cmapwordtoptr-class"></a>Класс CMapWordToPtr

Поддерживает сопоставления пустым указателям, зашифрованным 16-разрядными ключевыми словами.

## <a name="syntax"></a>Синтаксис

```
class CMapWordToPtr : public CObject
```

## <a name="members"></a>Участники

Функции-члены `CMapWordToPtr` похожи на функции-члены класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Если вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, заменить указатель на **void**. Если вы видите `CString` или **const** указатель на **char** как параметр функции или возвращаемое значение, замените слово.

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

, например, преобразуется в

`BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает число элементов в данном сопоставлении.|
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее число элементов в хэш-таблице.|
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Получает следующий элемент для выполнения итерации.|
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает число элементов в данном сопоставлении.|
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает позицию первого элемента.|
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблице.|
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Проверяет условие сопоставления пустым (нет элементов).|
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет указатель void на основе ключа указателя типа void. Значение указателя, а не сущности, которую он указывает, используется для сравнения ключей.|
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из данного сопоставления.|
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный с помощью ключа.|
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в карте — оператор подстановки для `SetAt`.|

## <a name="remarks"></a>Примечания

`CMapWordToPtr` включает в себя implement_dynamic-макрос для поддержки доступа типа времени выполнения и Сохранение дампа `CDumpContext` объекта. Если вам требуется дамп отдельных элементов карты, необходимо присвоить глубины контекста дампа 1 или более поздней версии.

Невозможно сериализовать указатель слова карт.

Когда `CMapWordToPtr` объект удаляется, или при его элементы удаляются, слов и указателей, удаляются. Сущностей, упоминаемых указатели не удаляются.

Дополнительные сведения о `CMapWordToPtr`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapWordToPtr`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

