---
title: Класс CMapStringToString
ms.date: 11/04/2016
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
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
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
helpviewer_keywords:
- CMapStringToString [MFC], CPair
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
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
ms.openlocfilehash: 754232ea57a77b4eb37a72ff98a3150419d0a248
ms.sourcegitcommit: 53f75afaf3c0b3ed481c5503357ed2b7b87aac6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2018
ms.locfileid: "53657374"
---
# <a name="cmapstringtostring-class"></a>Класс CMapStringToString

Поддерживает сопоставления объектов `CString` , зашифрованных объектами `CString` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToString : public CObject
```

## <a name="members"></a>Участники

Функции-члены `CMapStringToString` похожи на функции-члены класса [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Из-за этой схожести для изучения этой функции-члена можно использовать справочную документацию по классу `CMapStringToOb`. Если вы видите `CObject` указатель как возвращаемое значение или «выходной» параметр, функции, замените указатель на **char**. Если вы видите `CObject` указатель как параметр функции «input», замените указатель на **char**.

`BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`

, например, преобразуется в

`BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`

### <a name="public-structures"></a>Открытые структуры

|name|Описание:|
|----------|-----------------|
|[CMapStringToString::CPair](#cpair)|Вложенные структура, содержащая значение ключа и значения связанных строковых объекта.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
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
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый `CString` в сопоставлении.|
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Получает указатель на следующий `CString` для выполнения итерации.|
|[CMapStringToString::PLookup](#plookup)|Возвращает указатель на `CString` , значение которого совпадает с указанным значением.|
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Удаляет все элементы из данного сопоставления.|
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Удаляет элемент, указанный с помощью ключа.|
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CMapStringToOb::operator \[ \]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Вставляет элемент в карте — оператор подстановки для `SetAt`.|

## <a name="remarks"></a>Примечания

`CMapStringToString` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, карты, хранящегося в архив, либо с помощью перегруженных вставки ( **<<**) оператор или с `Serialize` функция-член.

Если вам требуется дамп отдельных `CString` -  `CString` элементов, необходимо задать глубины контекста дампа 1 или более поздней версии.

Когда `CMapStringToString` объект удаляется или когда его элементы удаляются, `CString` объекты удаляются в зависимости от ситуации.

Дополнительные сведения о `CMapStringToString`, см. в статье [коллекций](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToString`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

##  <a name="cpair"></a>  CMapStringToString::CPair

Содержит значение ключа и значения связанных строковых объекта.

### <a name="remarks"></a>Примечания

Это вложенную структуру в классе [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).

Структура состоит из двух полей:

- `key` Фактическое значение данного типа ключа.

- `value` Значение связанного объекта.

Он используется для хранения возвращаемого значения из [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), и [CMapStringToString::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Пример

  Пример использования, см. пример для [CMapStringToString::PLookup](#plookup).

##  <a name="pgetfirstassoc"></a>  CMapStringToString::PGetFirstAssoc

Возвращает первый элемент объекта map.

```
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первой записью в сопоставление; см. в разделе [CMapStringToString::CPair](#cpair). Если сопоставление является пустым, значение равно NULL.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для возврата указателя на первый элемент в объекте map.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]

##  <a name="pgetnextassoc"></a>  CMapStringToString::PGetNextAssoc

Извлекает элемент карты, на которые указывают *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssoc) const;

CPair *PGetNextAssoc(const CPair* pAssoc);
```

### <a name="parameters"></a>Параметры

*pAssoc*<br/>
Указывает на запись сопоставления, возвращенное предыдущим [PGetNextAssoc](#pgetnextassoc) или [PGetFirstAssoc](#pgetfirstassoc) вызова.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующую запись в сопоставление; см. в разделе [CMapStringToString::CPair](#cpair). Если элемент является последним в схеме, значение равно NULL.

### <a name="remarks"></a>Примечания

Этот метод используется для перебора всех элементов в сопоставлении. Получение первого элемента с помощью вызова `PGetFirstAssoc` и затем выполните итерацию через схему при последующих вызовах для `PGetNextAssoc`.

### <a name="example"></a>Пример

  См. в примере [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).

##  <a name="plookup"></a>  CMapStringToString::PLookup

Ищет значение, сопоставленное с данным ключом.

```
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Указатель на ключ для элемента для поиска.

### <a name="return-value"></a>Возвращаемое значение

Указатель на указанный ключ.

### <a name="remarks"></a>Примечания

Этот метод используется для поиска элемента карты с ключом, который точно соответствует заданному ключу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)

