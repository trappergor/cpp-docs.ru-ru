---
title: Класс CMapStringToString
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
- AFXCOLL/CMapStringToString::CMapStringToString
- AFXCOLL/CMapStringToString::GetCount
- AFXCOLL/CMapStringToString::GetHashTableSize
- AFXCOLL/CMapStringToString::GetNextAssoc
- AFXCOLL/CMapStringToString::GetSize
- AFXCOLL/CMapStringToString::GetStartPosition
- AFXCOLL/CMapStringToString::HashKey
- AFXCOLL/CMapStringToString::InitHashTable
- AFXCOLL/CMapStringToString::IsEmpty
- AFXCOLL/CMapStringToString::Lookup
- AFXCOLL/CMapStringToString::LookupKey
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToString::RemoveAll
- AFXCOLL/CMapStringToString::RemoveKey
- AFXCOLL/CMapStringToString::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
- CMapStringToString [MFC], CMapStringToString
- CMapStringToString [MFC], GetCount
- CMapStringToString [MFC], GetHashTableSize
- CMapStringToString [MFC], GetNextAssoc
- CMapStringToString [MFC], GetSize
- CMapStringToString [MFC], GetStartPosition
- CMapStringToString [MFC], HashKey
- CMapStringToString [MFC], InitHashTable
- CMapStringToString [MFC], IsEmpty
- CMapStringToString [MFC], Lookup
- CMapStringToString [MFC], LookupKey
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToString [MFC], RemoveAll
- CMapStringToString [MFC], RemoveKey
- CMapStringToString [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 544154569c50369b805ba296aa975849f245d4ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370117"
---
# <a name="cmapstringtostring-class"></a>Класс CMapStringToString

Поддерживает сопоставления объектов `CString` , зашифрованных объектами `CString` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Участники

Функции `CMapStringToString` члена аналогичны функциям-членам класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Везде, где `CObject` вы видите указатель в качестве значения возврата или параметра функции "выход", замените указатель на **символ.** Везде, где `CObject` вы видите указатель в качестве параметра функции "ввода", замените указатель на **символ.**

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

, например, преобразуется в

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

### <a name="public-structures"></a>Общественные структуры

|Имя|Описание|
|----------|-----------------|
|[CMapstringTostring::CPair](#cpair)|Вложенная структура, содержащая ключевое значение и значение связанного объекта строки.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMapstringtostring::Cmapstringtostring](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMapstringTostring::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Возвращает количество элементов на этой карте.|
|[CMapStringToString::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Определяет текущее количество элементов в таблице хэша.|
|[CMapstringTostring::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Получает следующий элемент для итерации.|
|[CMapstringtostring::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Возвращает количество элементов на этой карте.|
|[CMapstringtostring::GetStartposition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|Возвращает положение первого элемента.|
|[CMapStringToString::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Рассчитывает хэш-значение указанного ключа.|
|[CMapStringToString::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Инициализирует хэш-таблицу.|
|[CMapstringtostring::Isempty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Тесты на состояние пустой карты (без элементов).|
|[CMapstringToString::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Ищет пустоту указатель на основе ключа указателя пустоты. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[CMapstringToString::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[CMapstringTostring::PGetFirstAssoc](#pgetfirstassoc)|Получает указатель на `CString` первый на карте.|
|[CMapstringTostring::PGetNextAssoc](#pgetnextassoc)|Получает указатель на `CString` следующий для итерации.|
|[CMapstringToString::PLookup](#plookup)|Возвращает указатель в `CString` значение, значение которого соответствует указанному значению.|
|[CMapstringTostring::Removeall](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы с этой карты.|
|[CMapstringTostring::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный ключом.|
|[CMapstringTostring::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент на карту; заменяет существующий элемент при обнаружении соответствующего ключа.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CMapStringTostring::оператор \[\]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в карту - `SetAt`замена оператора для .|

## <a name="remarks"></a>Remarks

`CMapStringToString` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется по очереди, если карта хранится в архиве, либо с перегруженной вставкой () **<<** оператором или с функцией `Serialize` члена.

Если вам нужна свалка отдельных `CString` -  `CString` элементов, необходимо установить глубину контекста дампа до 1 или более.

Когда `CMapStringToString` объект удаляется или когда его элементы `CString` удаляются, объекты удаляются по мере необходимости.

Для получения `CMapStringToString`дополнительной информации о , см. [Collections](../../mfc/collections.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

## <a name="cmapstringtostringcpair"></a><a name="cpair"></a>CMapstringTostring::CPair

Содержит ключевое значение и значение связанного объекта строки.

### <a name="remarks"></a>Remarks

Это вложенная структура в классе [CMapStringToString.](../../mfc/reference/cmapstringtostring-class.md)

Структура состоит из двух полей:

- `key`Фактическое значение ключевого типа.

- `value`Значение связанного объекта.

Он используется для хранения значений возврата от [CMapStringToString: :PLookup](#plookup), [CMapStringToString: :PGetFirstAssoc](#pgetfirstassoc), и [CMapStringToString: :PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Пример

  Для примера использования см. пример [CMapStringToString::PLookup](#plookup).

## <a name="cmapstringtostringpgetfirstassoc"></a><a name="pgetfirstassoc"></a>CMapstringTostring::PGetFirstAssoc

Возвращает первую запись объекта карты.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первую запись на карте; [см. CmapstringTostring::CPair](#cpair). Если карта пуста, значение NULL.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы вернуть указатель первого элемента объекта карты.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

## <a name="cmapstringtostringpgetnextassoc"></a><a name="pgetnextassoc"></a>CMapstringTostring::PGetNextAssoc

Извлекает элемент карты, на который указывает *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Параметры

*pAssoc*<br/>
Очки на запись карты, возвращенную предыдущим вызовом [PGetNextAssoc](#pgetnextassoc) или [PGetFirstAssoc.](#pgetfirstassoc)

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующую запись на карте; [см. CmapstringTostring::CPair](#cpair). Если элемент является последним на карте, значение NULL.

### <a name="remarks"></a>Remarks

Назовите этот метод итератом через все элементы карты. Извлеките первый элемент `PGetFirstAssoc` с вызовом, а затем итерировать через карту с последовательными вызовами. `PGetNextAssoc`

### <a name="example"></a>Пример

  Смотрите пример [CMapStringToString: :PGetFirstAssoc](#pgetfirstassoc).

## <a name="cmapstringtostringplookup"></a><a name="plookup"></a>CMapstringToString::PLookup

Ищет значение, отображено к заданного ключу.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Указатель на ключ для элемента, который будет искать.

### <a name="return-value"></a>Возвращаемое значение

Указатель на указанный ключ.

### <a name="remarks"></a>Remarks

Вызовите этот метод для поиска элемента карты с ключом, который точно соответствует заданного ключа.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>См. также раздел

[MFC Образец COLLECT](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
