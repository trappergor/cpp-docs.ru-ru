---
title: Класс CMapStringToPtr
ms.date: 11/04/2016
f1_keywords:
- CMapStringToPtr
- AFXCOLL/CMapStringToPtr
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
ms.assetid: 1ac11143-eb0a-4511-a662-2df0d1d9005b
ms.openlocfilehash: 80e4ec92376559933b4e5a6d271d772da02bca82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62252929"
---
# <a name="cmapstringtoptr-class"></a>Класс CMapStringToPtr

Поддерживает сопоставления пустых указателей, зашифрованных объектами `CString` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToPtr : public CObject
```

## <a name="members"></a>Участники

Функции-члены `CMapStringToPtr` похожи на функции-члены класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Если вы видите `CObject` указатель в качестве параметра функции или возвращаемого значения, заменить указатель на **void**.

`BOOL CMapStringToOb::Lookup( const char* <key>, CObject*& <rValue> ) const;`

, например, преобразуется в

`BOOL CMapStringToPtr::Lookup( LPCTSTR <key>, void*& <rValue> ) const;`

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
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

|name|Описание|
|----------|-----------------|
|[CMapStringToOb::operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в карте — оператор подстановки для `SetAt`.|

## <a name="remarks"></a>Примечания

`CMapStringToPtr` включает в себя implement_dynamic-макрос для поддержки доступа типа времени выполнения и Сохранение дампа `CDumpContext` объекта. Если вам требуется дамп отдельных элементов карты, необходимо присвоить глубины контекста дампа 1 или более поздней версии.

Невозможно сериализовать maps указатель строки.

Когда `CMapStringToPtr` объект удаляется или когда его элементы удаляются, `CString` ключевые объекты и слова будут удалены.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToPtr`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
