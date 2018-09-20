---
title: Класс CMapStringToOb | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d00faec0ac65ded0c8e4ddc9f1ab50796bdecd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396328"
---
# <a name="cmapstringtoob-class"></a>Класс CMapStringToOb

Класс коллекции словаря, который сопоставляет уникальные объекты `CString` с указателями `CObject` .

## <a name="syntax"></a>Синтаксис

```
class CMapStringToOb : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Конструктор.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMapStringToOb::GetCount](#getcount)|Возвращает число элементов в данном сопоставлении.|
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Определяет текущее число элементов в хэш-таблице.|
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|
|[CMapStringToOb::GetSize](#getsize)|Возвращает число элементов в данном сопоставлении.|
|[CMapStringToOb::GetStartPosition](#getstartposition)|Возвращает позицию первого элемента.|
|[CMapStringToOb::HashKey](#hashkey)|Вычисляет хэш-значение указанного ключа.|
|[CMapStringToOb::InitHashTable](#inithashtable)|Инициализирует хэш-таблице.|
|[CMapStringToOb::IsEmpty](#isempty)|Проверяет условие сопоставления пустым (нет элементов).|
|[CMapStringToOb::Lookup](#lookup)|Ищет указатель void на основе ключа указателя типа void. Значение указателя, а не сущности, которую он указывает, используется для сравнения ключей.|
|[CMapStringToOb::LookupKey](#lookupkey)|Возвращает ссылку на ключ, связанный с указанным значением ключа.|
|[CMapStringToOb::RemoveAll](#removeall)|Удаляет все элементы из данного сопоставления.|
|[CMapStringToOb::RemoveKey](#removekey)|Удаляет элемент, указанный с помощью ключа.|
|[CMapStringToOb::SetAt](#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[[CMapStringToOb::operator]](#operator_at)|Вставляет элемент в карте — оператор подстановки для `SetAt`.|

## <a name="remarks"></a>Примечания

После вставки `CString` -  `CObject*` пары (элемент) в сопоставление, можно эффективно извлекать и удалять пары, используя строку или `CString` значение в качестве ключа. Можно также выполнить итерацию по всем элементам в карте.

Переменная типа ПОЗИЦИИ используется для доступа к альтернативную запись в все варианты карты. Можно использовать ПОЗИЦИЮ для «запомнить» запись и для выполнения итерации по карте. Можно подумать, что эта итерация выполняется последовательно по значению ключа; Нет. Последовательность элементов, полученных не определен.

`CMapStringToOb` использует макрос `IMPLEMENT_SERIAL` для поддержки сериализации и записи элементов в дамп. Каждый элемент сериализуется в свою очередь, карты, хранящегося в архив, либо с помощью перегруженных вставки ( **<<**) оператор или с `Serialize` функция-член.

Если вам требуется диагностики дамп отдельных элементов в сопоставлении ( `CString` значение и `CObject` содержимое), необходимо задать глубины контекста дампа 1 или более поздней версии.

Когда `CMapStringToOb` объект удаляется или когда его элементы удаляются, `CString` объектов и `CObject` указатели, удаляются. Объекты, на которые ссылается `CObject` указатели, не удаляются.

Для создания производного класса Map похож на список наследования. См. в статье [коллекций](../../mfc/collections.md) иллюстрация наследования класса списка специального назначения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMapStringToOb`

## <a name="requirements"></a>Требования

**Заголовок:** afxcoll.h

##  <a name="cmapstringtoob"></a>  CMapStringToOb::CMapStringToOb

Создает пустой `CString`- к - `CObject*` карты.

```
CMapStringToOb(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Указывает гранулярность выделения памяти для расширения карты.

### <a name="remarks"></a>Примечания

По мере роста карты памяти выделяется в единицах *nBlockSize* записей.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb:: CMapStringToOb`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

##  <a name="getcount"></a>  CMapStringToOb::GetCount

Определяет, какое количество элементов в сопоставлении.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в данном сопоставлении.

### <a name="remarks"></a>Примечания

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::GetCount`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; INT_PTR GetCount)**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; INT_PTR GetCount)**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; INT_PTR GetCount)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; INT_PTR GetCount)**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; INT_PTR GetCount)**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; INT_PTR GetCount)**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]

##  <a name="gethashtablesize"></a>  CMapStringToOb::GetHashTableSize

Определяет текущее число элементов в хэш-таблице.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число элементов в хэш-таблице.

### <a name="remarks"></a>Примечания

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::GetHashTableSize`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Const; () GetHashTableSize целое число без знака**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Const; () GetHashTableSize целое число без знака**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Const; () GetHashTableSize целое число без знака**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Const; () GetHashTableSize целое число без знака**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Const; () GetHashTableSize целое число без знака**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Const; () GetHashTableSize целое число без знака**|

##  <a name="getnextassoc"></a>  CMapStringToOb::GetNextAssoc

Извлекает элемент карты по *rNextPosition*, а затем обновляет *rNextPosition* для обращения к следующему элементу в сопоставлении.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    CString& rKey,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Параметры

*rNextPosition*<br/>
Задает ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetNextAssoc` или `GetStartPosition` вызова.

*rKey*<br/>
Указывает возвращаемый ключ полученного элемента (строка).

*rValue*<br/>
Указывает возвращаемое значение полученного элемента ( `CObject` указатель). Дополнительные сведения об этом параметре см. примечания.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для перебора всех элементов в сопоставлении. Обратите внимание на то, что последовательность позиция не обязательно так же, как последовательности значение ключа.

Если полученного элемента является последним в сопоставлении, то новое значение *rNextPosition* имеет значение NULL.

Для *rValue* параметр, убедитесь, что приведение типа объекта, чтобы **CObject\*&**, который является то, что компилятор требует, как показано в следующем примере:

[!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]

Это справедливо не для `GetNextAssoc` для карт на основе шаблонов.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::GetNextAssoc`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (положение &** *rNextPosition* **, void\* &**  *rKey* **, void\* &**  *rValue* **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (положение &** *rNextPosition* **, void\* &**  *rKey* **, WORD и** *rValue* **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (положение &** *rNextPosition* **, CString &** *rKey* **, void\* &**  *rValue* **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (положение &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (положение &** *rNextPosition* **, WORD &** *rKey* **, CObject\* &**  *rValue* **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (положение &** *rNextPosition* **, WORD &** *rKey* **, void\* &**  *rValue* **) const;**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]

Далее приведены результаты из этой программы.

```Output
Lisa : a CAge at $4724 11
Marge : a CAge at $47A8 35
Homer : a CAge at $4766 36
Bart : a CAge at $45D4 13
```

##  <a name="getsize"></a>  CMapStringToOb::GetSize

Возвращает количество элементов карты.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в сопоставлении.

### <a name="remarks"></a>Примечания

Вызовите этот метод для получения числа элементов в сопоставлении.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::GetSize`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; INT_PTR GetSize)**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; INT_PTR GetSize)**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; INT_PTR GetSize)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; INT_PTR GetSize)**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; INT_PTR GetSize)**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; INT_PTR GetSize)**|

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]

##  <a name="getstartposition"></a>  CMapStringToOb::GetStartPosition

Начинает итерацию карты, возвращая значение ПОЗИЦИИ, который может быть передан в `GetNextAssoc` вызова.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПОЗИЦИЯ значение, указывающее начальную позицию для выполнения итерации карты; или значение NULL, если сопоставление является пустым.

### <a name="remarks"></a>Примечания

В последовательности итерации не является прогнозируемым; Таким образом «первый элемент в сопоставлении» не имеет особой важности.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::GetStartPosition`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; ПОЗИЦИЯ GetStartPosition)**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; ПОЗИЦИЯ GetStartPosition)**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; ПОЗИЦИЯ GetStartPosition)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; ПОЗИЦИЯ GetStartPosition)**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; ПОЗИЦИЯ GetStartPosition)**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; ПОЗИЦИЯ GetStartPosition)**|

### <a name="example"></a>Пример

См. в примере [CMapStringToOb::GetNextAssoc](#getnextassoc).

##  <a name="hashkey"></a>  CMapStringToOb::HashKey

Вычисляет хэш-значение указанного ключа.

```
UINT HashKey(LPCTSTR key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, значение которого хэш вычисляться.

### <a name="return-value"></a>Возвращаемое значение

Значение хэша ключа

### <a name="remarks"></a>Примечания

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::HashKey`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**HashKey целое число без знака (void** <strong>\*</strong> `key` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**HashKey целое число без знака (void** <strong>\*</strong> `key` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**HashKey целое число без знака (LPCTSTR** `key` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**HashKey целое число без знака (LPCTSTR** `key` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**HashKey целое число без знака (WORD** `key` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**HashKey целое число без знака (WORD** `key` **) const;**|

##  <a name="inithashtable"></a>  CMapStringToOb::InitHashTable

Инициализирует хэш-таблице.

```
void InitHashTable(
    UINT hashSize,
    BOOL bAllocNow = TRUE);
```

### <a name="parameters"></a>Параметры

*hashSize*<br/>
Количество записей в хэш-таблице.

*bAllocNow*<br/>
Если значение равно TRUE, выделяет хэш-таблице при инициализации; в противном случае она выделяется при необходимости.

### <a name="remarks"></a>Примечания

Для наилучшей производительности размер хэш-таблицы должен быть простое число. Чтобы свести к минимуму конфликты, размер необходимо примерно 20 процентов, размер которых превышает наибольший ожидаемый набор данных.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::InitHashTable`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (целое число без знака** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (целое число без знака** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (целое число без знака** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (целое число без знака** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (целое число без знака** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (целое число без знака** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|

##  <a name="isempty"></a>  CMapStringToOb::IsEmpty

Определяет, является ли сопоставление является пустым.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если эта карта не содержит элементов; в противном случае 0.

### <a name="example"></a>Пример

См. в примере [RemoveAll](#removeall).

### <a name="remarks"></a>Примечания

В следующей таблице показаны другой член функции, которые похожи на **CMapStringToOb:: IsEmpty**.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**(Const; BOOL IsEmpty)**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**(Const; BOOL IsEmpty)**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**(Const; BOOL IsEmpty)**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**(Const; BOOL IsEmpty)**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**(Const; BOOL IsEmpty)**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**(Const; BOOL IsEmpty)**|

##  <a name="lookup"></a>  CMapStringToOb::Lookup

Возвращает `CObject` на основе указателя `CString` значение.

```
BOOL Lookup(
    LPCTSTR key,
    CObject*& rValue) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Указывает Искомый строковый ключ, который определяет элемент, выполняется поиск.

*rValue*<br/>
Указывает возвращаемое значение из искомого элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент найден; в противном случае 0.

### <a name="remarks"></a>Примечания

`Lookup` использует алгоритм хэширования для быстрого поиска элемента карты с ключом, обеспечивающее точное совпадение ( `CString` значение).

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::LookUp`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Поиск BOOL (void** <strong>\*</strong> `key` **, void\* &**  `rValue` **) const;**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Поиск BOOL (void** <strong>\*</strong> `key` **, WORD &** `rValue` **) const;**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Поиск BOOL (LPCTSTR** `key` **, void\* &**  `rValue` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Поиск BOOL (LPCTSTR** `key` **, CString &** `rValue` **) const;**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Поиск BOOL (WORD** `key` **, CObject\* &**  `rValue` **) const;**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Поиск BOOL (WORD** `key` **, void\* &**  `rValue` **) const;**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]

##  <a name="lookupkey"></a>  CMapStringToOb::LookupKey

Возвращает ссылку на ключ, связанный с указанным значением ключа.

```
BOOL LookupKey(
    LPCTSTR key,
    LPCTSTR& rKey) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Указывает Искомый строковый ключ, который определяет элемент, выполняется поиск.

*rKey*<br/>
Ссылка на связанный ключ.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если ключ найден; в противном случае 0.

### <a name="remarks"></a>Примечания

С помощью ссылки на ключ небезопасна в том случае, если используется после удаления связанного элемента из карты или карты был удален.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb:: LookupKey`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL поля оставлены пустыми (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL поля оставлены пустыми (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|

##  <a name="operator_at"></a>  CMapStringToOb::operator [ ]

Удобный заменой `SetAt` функция-член.

```
CObject*& operator[ ](lpctstr key);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на указатель на `CObject` объект или значение NULL, если сопоставление является пустым или *ключ* выходит за пределы диапазона.

### <a name="remarks"></a>Примечания

Таким образом он может использоваться только в левой части оператора присваивания (l значение). Если ни один элемент карты с указанным ключом, то создается новый элемент.

Нет нет» справа от оператора» (r-значение) эквивалентно этот оператор так как есть вероятность, что ключ не может находиться в схеме. Используйте `Lookup` функция-член для извлечения элемента.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::operator []`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|<strong>void\*& оператор\[] (void \*</strong>  `key`  **\);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Оператор & WORD\[] (void** <strong>\*</strong> `key`  **\);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& оператор\[] (lpctstr** `key`  **\);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & оператор\[] (lpctstr** `key`  **\);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& оператор\[] (word** `key`  **\);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& оператор\[] (word** `key`  **\);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]

Далее приведены результаты из этой программы.

```Output
Operator [] example: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $4A02 11
[Bart] = a CAge at $497E 13
```

##  <a name="removeall"></a>  CMapStringToOb::RemoveAll

Удаляет все элементы с помощью этой карты и уничтожает `CString` основные объекты.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

`CObject` Объекты, упоминаемые каждый ключ, не удаляются. `RemoveAll` Функции может вызвать утечку памяти, если вы не убедитесь, что упоминаемая `CObject` объекты уничтожаются.

Функция правильно работает, если сопоставление уже является пустым.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::RemoveAll`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void (RemoveAll);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void (RemoveAll);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void (RemoveAll);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void (RemoveAll);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void (RemoveAll);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void (RemoveAll);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]

##  <a name="removekey"></a>  CMapStringToOb::RemoveKey

Ищет запись сопоставления, соответствующий заданному ключу; затем Если ключ найден, удаляет запись.

```
BOOL RemoveKey(LPCTSTR key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Указывает строку, которая используется для просмотра карты.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был найден и успешно удален; в противном случае 0.

### <a name="remarks"></a>Примечания

Это может вызвать утечку памяти, если `CObject` объект не удаляется в другом месте.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::RemoveKey`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void** <strong>\*</strong> `key` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]

Далее приведены результаты из этой программы.

```Output
RemoveKey example: A CMapStringToOb with 3 elements
[Marge] = a CAge at $49A0 35
[Homer] = a CAge at $495E 36
[Bart] = a CAge at $4634 13
```

##  <a name="setat"></a>  CMapStringToOb::SetAt

Основным средством для вставки элемента в сопоставлении.

```
void SetAt(
    LPCTSTR key,
    CObject* newValue);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Задает строку, которая является ключом нового элемента.

*новое значение*<br/>
Указывает `CObject` указатель, который является значением нового элемента.

### <a name="remarks"></a>Примечания

Во-первых ищется ключ. Если ключ найден, а затем соответствующее значение изменяется; в противном случае создается новый элемент ключ значение.

В следующей таблице показаны другой член функции, которые похожи на `CMapStringToOb::SetAt`.

|Класс|Функция-член|
|-----------|---------------------|
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt (void** <strong>\*</strong> `key` **, WORD** `newValue` **);**|
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void** <strong>\*</strong> `newValue` **);**|
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (WORD** `key` **, CObject** <strong>\*</strong> `newValue` **);**|
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (WORD** `key` **, void** <strong>\*</strong> `newValue` **);**|

### <a name="example"></a>Пример

См. в разделе [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) список `CAge` класс, используемый во всех примерах в коллекции.

[!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]

Далее приведены результаты из этой программы.

```Output
before Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $493C 11
[Bart] = a CAge at $4654 13
after Lisa's birthday: A CMapStringToOb with 2 elements
[Lisa] = a CAge at $49C0 12
[Bart] = a CAge at $4654 13
```

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)<br/>
[Класс CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)<br/>
[Класс CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)<br/>
[Класс CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)
