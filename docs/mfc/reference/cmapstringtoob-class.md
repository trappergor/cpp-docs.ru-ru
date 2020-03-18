---
title: Класс Кмапстрингтуб
ms.date: 11/04/2016
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
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
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
ms.openlocfilehash: b56e9052533269ba62d248312f07ac16db71bf4a
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424323"
---
# <a name="cmapstringtoob-class"></a>Класс Кмапстрингтуб

Класс коллекции словаря, который сопоставляет уникальные объекты `CString` с указателями `CObject` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кмапстрингтуб:: Кмапстрингтуб](#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кмапстрингтуб:: NOCOUNT](#getcount)|Возвращает число элементов в этой карте.|
|[Кмапстрингтуб:: Жесаштаблесизе](#gethashtablesize)|Определяет текущее количество элементов в хэш-таблице.|
|[Кмапстрингтуб:: Жетнекстассок](#getnextassoc)|Возвращает следующий элемент для итерации.|
|[Кмапстрингтуб:: DataSize](#getsize)|Возвращает число элементов в этой карте.|
|[Кмапстрингтуб:: Жетстартпоситион](#getstartposition)|Возвращает расположение первого элемента.|
|[Кмапстрингтуб:: Хашкэй](#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[Кмапстрингтуб:: Инисаштабле](#inithashtable)|Инициализирует хэш-таблицу.|
|[Кмапстрингтуб:: IsEmpty](#isempty)|Проверяет условие на пустую карту (нет элементов).|
|[Кмапстрингтуб:: Lookup](#lookup)|Ищет указатель void на основе ключа указателя void. Значение указателя, а не сущность, на которое он указывает, используется для сравнения ключей.|
|[Кмапстрингтуб:: LookupKey](#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[Кмапстрингтуб:: RemoveAll](#removeall)|Удаляет все элементы из этой схемы.|
|[Кмапстрингтуб:: Ремовекэй](#removekey)|Удаляет элемент, указанный ключом.|
|[Кмапстрингтуб:: SetAt](#setat)|Вставляет элемент в карту; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[Кмапстрингтуб:: operator \[ \]](#operator_at)|Вставляет элемент в Map — подстановку оператора для `SetAt`.|

## <a name="remarks"></a>Remarks

После вставки `CString`- `CObject*` пары (element) в карту можно эффективно получить или удалить пару, используя строку или значение `CString` в качестве ключа. Можно также выполнить итерацию по всем элементам на карте.

Переменная типа "расположение" используется для альтернативного доступа к записи во всех вариантах карт. Можно использовать точку для «запомнить» запись и выполнить итерацию по карте. Можно подумать, что эта итерация выполняется последовательно по значению ключа; Нет. Последовательность извлеченных элементов является неопределенной.

`CMapStringToOb` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, если схема хранится в архиве с помощью перегруженного оператора вставки ( **<<** ) или с помощью функции-члена `Serialize`.

Если требуется диагностический дамп отдельных элементов на карте (`CString` значение и содержимое `CObject`), необходимо задать глубину контекста дампа 1 или более.

При удалении объекта `CMapStringToOb` или удалении его элементов происходит удаление `CString` объектов и `CObject`ных указателей. Объекты, на которые ссылаются указатели `CObject`, не уничтожаются.

Наследование класса Map аналогично наследованию списка. Сведения о наследовании класса специального списка см. в статье [коллекции](../../mfc/collections.md) статей.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Требования

**Заголовок:** афксколл. h

##  <a name="cmapstringtoob"></a>Кмапстрингтуб:: Кмапстрингтуб

Конструирует пустую карту `CString`-`CObject*`.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*нблокксизе*<br/>
Задает гранулярность выделения памяти для расширения схемы.

### <a name="remarks"></a>Remarks

По мере роста схемы память выделяется в единицах *нблокксизе* записей.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb:: CMapStringToOb`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**Кмапптртоптр (INT_PTR** `nBlockSize` **= 10);**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**Кмапптртоворд (INT_PTR** `nBlockSize` **= 10);**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**Кмапстрингтоптр (INT_PTR** `nBlockSize` **= 10);**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Кмапстрингтостринг (INT_PTR** `nBlockSize` **= 10);**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**Кмапвордтуб (INT_PTR** `nBlockSize` **= 10);**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**Мапвордтоптр (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

##  <a name="getcount"></a>Кмапстрингтуб:: NOCOUNT

Определяет количество элементов на карте.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в этой карте.

### <a name="remarks"></a>Remarks

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::GetCount`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR вычислить const ();**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR вычислить const ();**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR вычислить const ();**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR вычислить const ();**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR вычислить const ();**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR вычислить const ();**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

##  <a name="gethashtablesize"></a>Кмапстрингтуб:: Жесаштаблесизе

Определяет текущее количество элементов в хэш-таблице.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов в хэш-таблице.

### <a name="remarks"></a>Remarks

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::GetHashTableSize`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**UINT Жесаштаблесизе () const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**UINT Жесаштаблесизе () const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**UINT Жесаштаблесизе () const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**UINT Жесаштаблесизе () const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**UINT Жесаштаблесизе () const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**UINT Жесаштаблесизе () const;**|

##  <a name="getnextassoc"></a>Кмапстрингтуб:: Жетнекстассок

Извлекает элемент Map по адресу *рнекстпоситион*, а затем обновляет *рнекстпоситион* для ссылки на следующий элемент в сопоставлении.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Параметры

*рнекстпоситион*<br/>
Задает ссылку на значение, возвращенное предыдущим `GetNextAssoc` или вызовом `GetStartPosition`.

*ркэй*<br/>
Указывает возвращаемый ключ извлеченного элемента (строка).

*rValue*<br/>
Задает возвращаемое значение полученного элемента (указатель `CObject`). Дополнительные сведения об этом параметре см. в разделе "Примечания".

### <a name="remarks"></a>Remarks

Эта функция наиболее полезна для прохода по всем элементам на карте. Обратите внимание, что последовательность позиций не обязательно совпадает с последовательностью значений ключа.

Если извлеченный элемент является последним в сопоставлении, то новое значение *рнекстпоситион* устанавливается в NULL.

Для параметра *rvalue* обязательно приведите тип объекта к типу **CObject\*&** , который требуется компилятору, как показано в следующем примере:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

Это не относится `GetNextAssoc` для карт, основанных на шаблонах.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::GetNextAssoc`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**void жетнекстассок (позиционирование &** *рнекстпоситион* **, void\*&** *ркэй* **, void\*&** *rvalue* **) const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**void жетнекстассок (позиционирование &** *рнекстпоситион* **, void\*&** *ркэй* **, Word &** *rvalue* **) const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**void жетнекстассок (позиционирование &** *рнекстпоситион* **, CString &** *ркэй* **, void\*&** *rvalue* **) const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**void жетнекстассок (позиционирование &** *рнекстпоситион* **, cstring &** *ркэй* **, CString &** *rvalue* **) const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**void жетнекстассок (позиционирование &** *рнекстпоситион* **, WORD &** *ркэй* **, CObject\*&** *rvalue* **) const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**void жетнекстассок (позиционирование &** *рнекстпоситион* **, WORD &** *ркэй* **, void\*&** *rvalue* **) const;**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

##  <a name="getsize"></a>Кмапстрингтуб:: DataSize

Возвращает число элементов Map.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в сопоставлении.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы получить количество элементов в сопоставлении.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::GetSize`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR-size () const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR-size () const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR-size () const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR-size () const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR-size () const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR-size () const;**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

##  <a name="getstartposition"></a>Кмапстрингтуб:: Жетстартпоситион

Запускает итерацию Map, возвращая значение расположения, которое может быть передано в вызов `GetNextAssoc`.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение положения, указывающее начальную точку для прохода по карте; или значение NULL, если схема пуста.

### <a name="remarks"></a>Remarks

Последовательность итераций не является прогнозируемой. Таким образом, «первый элемент на карте» не имеет особой значимости.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::GetStartPosition`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**Жетстартпоситион () const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**Жетстартпоситион () const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**Жетстартпоситион () const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Жетстартпоситион () const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**Жетстартпоситион () const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**Жетстартпоситион () const;**|

### <a name="example"></a>Пример

См. пример для [кмапстрингтуб:: жетнекстассок](#getnextassoc).

##  <a name="hashkey"></a>Кмапстрингтуб:: Хашкэй

Вычисляет хэш-значение указанного ключа.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, хэш-значение которого необходимо вычислить.

### <a name="return-value"></a>Возвращаемое значение

Хэш-значение ключа

### <a name="remarks"></a>Remarks

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::HashKey`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**Uint хашкэй (void** <strong>\*</strong> `key` **) const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**Uint хашкэй (void** <strong>\*</strong> `key` **) const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Uint хашкэй (LPCTSTR** `key` **) const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**Uint хашкэй (LPCTSTR** `key` **) const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**Uint хашкэй (слово** `key` **) const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**Uint хашкэй (слово** `key` **) const;**|

##  <a name="inithashtable"></a>Кмапстрингтуб:: Инисаштабле

Инициализирует хэш-таблицу.

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Параметры

*хашсизе*<br/>
Число записей в хэш-таблице.

*баллокнов*<br/>
Если значение — TRUE, при инициализации выделяется хэш-таблица. в противном случае таблица выделяется при необходимости.

### <a name="remarks"></a>Remarks

Для лучшей производительности размер хэш-таблицы должен быть простым числом. Чтобы избежать конфликтов, размер должен быть примерно на 20% больше, чем самый большой ожидаемый набор данных.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::InitHashTable`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**void инисаштабле (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**void инисаштабле (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**void инисаштабле (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**void инисаштабле (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**void инисаштабле (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**void инисаштабле (UINT** `hashSize` **, bool** `bAllocNow` **= true);**|

##  <a name="isempty"></a>Кмапстрингтуб:: IsEmpty

Определяет, пуста ли схема.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если эта схема не содержит элементов; в противном случае — 0.

### <a name="example"></a>Пример

См. пример для [RemoveAll](#removeall).

### <a name="remarks"></a>Remarks

В следующей таблице показаны другие функции элементов, аналогичные **кмапстрингтуб:: IsEmpty**.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL-Empty () const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**BOOL-Empty () const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL-Empty () const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**BOOL-Empty () const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**BOOL-Empty () const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL-Empty () const;**|

##  <a name="lookup"></a>Кмапстрингтуб:: Lookup

Возвращает указатель `CObject`, основанный на значении `CString`.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Задает ключ строки, определяющий элемент для поиска.

*rValue*<br/>
Указывает возвращаемое значение из просматриваемого элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент найден; в противном случае — 0.

### <a name="remarks"></a>Remarks

`Lookup` использует алгоритм хэширования для быстрого поиска элемента Map с ключом, точно соответствующим (`CString` значение).

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::LookUp`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**Bool Lookup (void** <strong>\*</strong> `key` **, void\*&** `rValue` **) const;**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**Bool Lookup (void** <strong>\*</strong> `key` **, Word &** `rValue` **) const;**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**Bool Lookup (LPCTSTR** `key` **, void\*&** `rValue` **) const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Логический просмотр (LPCTSTR** `key` **, CString &** `rValue` **) const;**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**Bool Lookup (WORD** `key` **, CObject\*&** `rValue` **) const;**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**Bool Lookup (WORD** `key` **, void\*&** `rValue` **) const;**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

##  <a name="lookupkey"></a>Кмапстрингтуб:: LookupKey

Возвращает ссылку на ключ, связанный с указанным значением ключа.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Задает ключ строки, определяющий элемент для поиска.

*ркэй*<br/>
Ссылка на связанный ключ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если ключ найден; в противном случае — 0.

### <a name="remarks"></a>Remarks

Использование ссылки на ключ является ненадежным, если используется после удаления связанного элемента из сопоставления или после уничтожения сопоставления.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb:: LookupKey`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**Bool LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Bool LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|

##  <a name="operator_at"></a>Кмапстрингтуб:: operator []

Удобное подстановка для функции-члена `SetAt`.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на указатель на объект `CObject`; или значение NULL, если схема пуста или *ключ* выходит за пределы допустимого диапазона.

### <a name="remarks"></a>Remarks

Поэтому его можно использовать только в левой части оператора присваивания (l-значение). Если элемент Map с указанным ключом отсутствует, создается новый элемент.

Нет "правого" (r-Value), эквивалентного этому оператору, так как существует вероятность, что ключ не может быть найден на карте. Используйте функцию члена `Lookup` для получения элементов.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::operator []`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*& operator\[] (void \*</strong> `key` **\);**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**Слово & оператор\[] (void** <strong>\*</strong> `key` **\);**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& operator\[] (lpctstr** `key` **\);**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Оператор & CString\[] (lpctstr** `key` **\);**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& operator\[] (word** `key` **\);**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& operator\[] (word** `key` **\);**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

##  <a name="removeall"></a>Кмапстрингтуб:: RemoveAll

Удаляет все элементы из этой схемы и уничтожает `CString` объекты ключей.

```
void RemoveAll();
```

### <a name="remarks"></a>Remarks

`CObject` объекты, на которые ссылается каждый ключ, не уничтожаются. Функция `RemoveAll` может вызвать утечку памяти, если не гарантировать, что связанные объекты `CObject` уничтожаются.

Функция работает правильно, если схема уже пуста.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::RemoveAll`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll ();**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll ();**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll ();**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll ();**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll ();**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

##  <a name="removekey"></a>Кмапстрингтуб:: Ремовекэй

Выполняет поиск записи Map, соответствующей заданному ключу; Затем, если ключ найден, удаляет запись.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Указывает строку, используемую для уточняющего запроса таблицы.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если запись была найдена и успешно удалена; в противном случае — 0.

### <a name="remarks"></a>Remarks

Это может вызвать утечку памяти, если объект `CObject` не удаляется в других местах.

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::RemoveKey`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**Bool ремовекэй (void** <strong>\*</strong> `key` **);**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**Bool ремовекэй (void** <strong>\*</strong> `key` **);**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**Bool ремовекэй (LPCTSTR** `key` **);**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**Bool ремовекэй (LPCTSTR** `key` **);**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**Bool ремовекэй (WORD** `key` **);**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**Bool ремовекэй (WORD** `key` **);**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

##  <a name="setat"></a>Кмапстрингтуб:: SetAt

Основной способ вставки элемента в карту.

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Задает строку, которая является ключом нового элемента.

*newValue*<br/>
Указывает `CObject`ный указатель, являющийся значением нового элемента.

### <a name="remarks"></a>Remarks

Во-первых, ищется ключ. Если ключ найден, соответствующее значение изменяется. в противном случае создается новый элемент "ключ-значение".

В следующей таблице показаны другие функции элементов, аналогичные `CMapStringToOb::SetAt`.

|Class|Функция-член|
|-----------|---------------------|
|[кмапптртоптр](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[кмапптртоворд](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, Word** `newValue` **);**|
|[кмапстрингтоптр](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[кмапстрингтостринг](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[кмапвордтуб](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[кмапвордтоптр](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Пример

Список `CAge` класса, используемого во всех примерах коллекции, см. в разделе [коблист:: коблист](../../mfc/reference/coblist-class.md#coblist) .

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

Результаты этой программы выглядят следующим образом:

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[Класс CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)<br/>
[Класс CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)<br/>
[Класс CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)
