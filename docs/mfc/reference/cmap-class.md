---
title: Класс CMap
ms.date: 11/04/2016
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
ms.openlocfilehash: 58f9efb19988be8487ec87ce0c63d90ee1a97911
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58769840"
---
# <a name="cmap-class"></a>Класс CMap

Класс коллекции словарей, который сопоставляет уникальные ключи значениям.

## <a name="syntax"></a>Синтаксис

```
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject
```

#### <a name="parameters"></a>Параметры

*KEY*<br/>
Класс объекта, используемое в качестве ключа к схеме.

*ARG_KEY*<br/>
Тип данных, используемый для *ключ* аргументы; обычно ссылка *ключ*.

*ЗНАЧЕНИЕ*<br/>
Класс объекта, хранимый в сопоставлении.

*ARG_VALUE*<br/>
Тип данных, используемый для *значение* аргументы; обычно ссылка *значение*.

## <a name="members"></a>Участники

### <a name="public-structures"></a>Открытые структуры

|name|Описание|
|----------|-----------------|
|[CMap::CPair](#cpair)|Вложенные структуру, содержащую ключевое значение и значение из связанного объекта.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CMap::CMap](#cmap)|Создает коллекцию, которая сопоставляет значения ключей.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CMap::GetCount](#getcount)|Возвращает число элементов в данном сопоставлении.|
|[CMap::GetHashTableSize](#gethashtablesize)|Возвращает число элементов в хэш-таблице.|
|[CMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|
|[CMap::GetSize](#getsize)|Возвращает число элементов в данном сопоставлении.|
|[CMap::GetStartPosition](#getstartposition)|Возвращает позицию первого элемента.|
|[CMap::InitHashTable](#inithashtable)|Инициализирует хэш-таблицы и ее размер.|
|[CMap::IsEmpty](#isempty)|Проверяет условие сопоставления пустым (нет элементов).|
|[CMap::Lookup](#lookup)|Ищет значение, сопоставленное с данным ключом.|
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Возвращает указатель на первый элемент.|
|[CMap::PGetNextAssoc](#pgetnextassoc)|Получает указатель на следующий элемент для выполнения итерации.|
|[CMap::PLookup](#plookup)|Возвращает указатель на ключ, значение которого совпадает с указанным значением.|
|[CMap::RemoveAll](#removeall)|Удаляет все элементы из данного сопоставления.|
|[CMap::RemoveKey](#removekey)|Удаляет элемент, указанный с помощью ключа.|
|[CMap::SetAt](#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CMap::operator \[ \]](#operator_at)|Вставляет элемент в карте — оператор подстановки для `SetAt`.|

## <a name="remarks"></a>Примечания

После вставки пару "ключ значение" (элемент) в сопоставление, можно эффективно извлекать и удалять пары, с помощью ключа для доступа к нему. Можно также выполнить итерацию по всем элементам в карте.

Переменная типа ПОЗИЦИИ используется для альтернативного доступа для записи. Можно использовать ПОЗИЦИЮ для «запомнить» запись и для выполнения итерации по карте. Можно подумать, что эта итерация выполняется последовательно по значению ключа; Нет. Последовательность элементов, полученных не определен.

Некоторые функции-члены этого класса вызова глобального вспомогательные функции, необходимо настроить для большинства вариантов использования `CMap` класса. См. в разделе [вспомогательные функции классов коллекции](../../mfc/reference/collection-class-helpers.md) макросы и глобальные объекты из раздела **Справочник по библиотеке MFC**.

`CMap` переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) для поддержки сериализации и записи элементов в дамп. Если карты хранится в архив с помощью `Serialize`, в свою очередь сериализуется каждого элемента карты. Реализация по умолчанию `SerializeElements` вспомогательная функция выполняет побитовое записи. Для сведений о сериализации указатель коллекции элементов, производных от `CObject` или другие пользовательские типы, см. в разделе [как: Создание безопасных типов коллекций](../../mfc/how-to-make-a-type-safe-collection.md).

Если вам требуется дамп диагностики отдельных элементов в сопоставлении (ключи и значения), необходимо присвоить глубины контекста дампа 1 или более поздней версии.

Когда `CMap` объект удаляется, или при его элементы удаляются, ключи и значения, удаляются.

Для создания производного класса Map похож на список наследования. См. в статье [коллекций](../../mfc/collections.md) иллюстрация наследования класса списка специального назначения.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CMap`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

##  <a name="cmap"></a>  CMap::CMap

Создает пустого сопоставления.

```
CMap(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Параметры

*nBlockSize*<br/>
Указывает гранулярность выделения памяти для расширения карты.

### <a name="remarks"></a>Примечания

По мере роста карты памяти выделяется в единицах *nBlockSize* записей.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]

##  <a name="cpair"></a>  CMap::CPair

Содержит значение ключа и значение из связанного объекта.

### <a name="remarks"></a>Примечания

Это вложенную структуру в классе [CMap](../../mfc/reference/cmap-class.md).

Структура состоит из двух полей:

- `key` Фактическое значение данного типа ключа.

- `value` Значение связанного объекта.

Он используется для хранения возвращаемого значения из [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), и [CMap::PGetNextAssoc](#pgetnextassoc).

### <a name="example"></a>Пример

Пример использования, см. пример для [CMap::PLookup](#plookup).

##  <a name="getcount"></a>  CMap::GetCount

Возвращает число элементов в объекте map.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество элементов

### <a name="example"></a>Пример

См. в примере [CMap::Lookup](#lookup).

##  <a name="gethashtablesize"></a>  CMap::GetHashTableSize

Определяет количество элементов в хэш-таблицу для карты.

```
UINT GetHashTableSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в хэш-таблице.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]

##  <a name="getnextassoc"></a>  CMap::GetNextAssoc

Извлекает элемент карты по `rNextPosition`, а затем обновляет `rNextPosition` для обращения к следующему элементу в сопоставлении.

```
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*rNextPosition*<br/>
Задает ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetNextAssoc` или `GetStartPosition` вызова.

*KEY*<br/>
Параметр шаблона, указывающий тип ключа карты.

*rKey*<br/>
Указывает возвращаемый ключ полученного элемента.

*ЗНАЧЕНИЕ*<br/>
Параметр шаблона, указывающий тип значения карты.

*rValue*<br/>
Указывает возвращаемое значение полученного элемента.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для перебора всех элементов в сопоставлении. Обратите внимание на то, что последовательность позиция не обязательно так же, как последовательности значение ключа.

Если полученного элемента является последним в сопоставлении, то новое значение *rNextPosition* имеет значение NULL.

### <a name="example"></a>Пример

См. в примере [CMap::SetAt](#setat).

##  <a name="getsize"></a>  CMap::GetSize

Возвращает количество элементов карты.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в сопоставлении.

### <a name="remarks"></a>Примечания

Вызовите этот метод для получения числа элементов в сопоставлении.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="getstartposition"></a>  CMap::GetStartPosition

Начинает итерацию карты, возвращая значение ПОЗИЦИИ, который может быть передан в `GetNextAssoc` вызова.

```
POSITION GetStartPosition() const;
```

### <a name="return-value"></a>Возвращаемое значение

ПОЗИЦИЯ значение, указывающее начальную позицию для выполнения итерации карты; или значение NULL, если сопоставление является пустым.

### <a name="remarks"></a>Примечания

В последовательности итерации не является прогнозируемым; Таким образом «первый элемент в сопоставлении» не имеет особой важности.

### <a name="example"></a>Пример

См. в примере [CMap::SetAt](#setat).

##  <a name="inithashtable"></a>  CMap::InitHashTable

Инициализирует хэш-таблице.

```
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);
```

### <a name="parameters"></a>Параметры

*hashSize*<br/>
Количество записей в хэш-таблице.

*bAllocNow*<br/>
Если значение равно TRUE, выделяет хэш-таблице при инициализации; в противном случае она выделяется при необходимости.

### <a name="remarks"></a>Примечания

Для наилучшей производительности размер хэш-таблицы должен быть простое число. Чтобы свести к минимуму конфликты, размер необходимо примерно 20 процентов, размер которых превышает наибольший ожидаемый набор данных.

### <a name="example"></a>Пример

См. в примере [CMap::Lookup](#lookup).

##  <a name="isempty"></a>  CMap::IsEmpty

Определяет, является ли сопоставление является пустым.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если эта карта не содержит элементов; в противном случае 0.

### <a name="example"></a>Пример

См. в примере [CMap::RemoveAll](#removeall).

##  <a name="lookup"></a>  CMap::Lookup

Ищет значение, сопоставленное с данным ключом.

```
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметр шаблона, указывающий тип *ключ* значение.

*key*<br/>
Задает ключ, определяющий элемент, выполняется поиск.

*ЗНАЧЕНИЕ*<br/>
Указывает тип значения, выполняется поиск.

*rValue*<br/>
Получает значение искомого.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент найден; в противном случае 0.

### <a name="remarks"></a>Примечания

`Lookup` использует алгоритм хэширования для быстрого поиска элемента карты с ключом, который точно соответствует заданному ключу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]

##  <a name="operator_at"></a>  [CMap::operator]

Удобный заменой `SetAt` функция-член.

```
VALUE& operator[](arg_key key);
```

### <a name="parameters"></a>Параметры

*ЗНАЧЕНИЕ*<br/>
Параметр шаблона, указывающий тип значения карты.

*ARG_KEY*<br/>
Параметр шаблона, указывающий тип значения ключа.

*key*<br/>
Ключ, используемый для извлечения значения из сопоставления.

### <a name="remarks"></a>Примечания

Таким образом он может использоваться только в левой части оператора присваивания (l значение). Если ни один элемент карты с указанным ключом, то создается новый элемент.

Нет нет» справа от оператора» (r-значение) эквивалентно этот оператор так как есть вероятность, что ключ не может находиться в схеме. Используйте `Lookup` функция-член для извлечения элемента.

### <a name="example"></a>Пример

См. в примере [CMap::Lookup](#lookup).

##  <a name="pgetfirstassoc"></a>  CMap::PGetFirstAssoc

Возвращает первый элемент объекта map.

```
const CPair* PGetFirstAssoc() const;
CPair* PGetFirstAssoc();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на первой записью в сопоставление; см. в разделе [CMap::CPair](#cpair). Если сопоставление содержит без элементов, значение равно NULL.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для возврата указателя на первый элемент в объекте map.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]

##  <a name="pgetnextassoc"></a>  CMap::PGetNextAssoc

Извлекает элемент карты, на которые указывают *pAssocRec*.

```
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;

CPair *PGetNextAssoc(const CPair* pAssocRet);
```

### <a name="parameters"></a>Параметры

*pAssocRet*<br/>
Указывает на запись сопоставления, возвращенное предыдущим [PGetNextAssoc](#pgetnextassoc) или [CMap::PGetFirstAssoc](#pgetfirstassoc) вызова.

### <a name="return-value"></a>Возвращаемое значение

Указатель на следующую запись в сопоставление; см. в разделе [CMap::CPair](#cpair). Если элемент является последним в схеме, значение равно NULL.

### <a name="remarks"></a>Примечания

Этот метод используется для перебора всех элементов в сопоставлении. Получение первого элемента с помощью вызова `PGetFirstAssoc` и затем выполните итерацию через схему при последующих вызовах для `PGetNextAssoc`.

### <a name="example"></a>Пример

См. в примере [CMap::PGetFirstAssoc](#pgetfirstassoc).

##  <a name="plookup"></a>  CMap::PLookup

Находит значение, сопоставленное с данным ключом.

```
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ элемента для поиска.

### <a name="return-value"></a>Возвращаемое значение

Указатель на структуру ключей; см. в разделе [CMap::CPair](#cpair). Если совпадений не найдено, `CMap::PLookup` возвращает значение NULL.

### <a name="remarks"></a>Примечания

Этот метод используется для поиска элемента карты с ключом, который точно соответствует заданному ключу.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]

##  <a name="removeall"></a>  CMap::RemoveAll

Удаляет все значения с помощью этой карты, вызвав функцию глобального `DestructElements`.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Функция правильно работает, если сопоставление уже является пустым.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]

##  <a name="removekey"></a>  CMap::RemoveKey

Ищет запись сопоставления, соответствующий заданному ключу; затем Если ключ найден, удаляет запись.

```
BOOL RemoveKey(ARG_KEY key);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметр шаблона, указывающий тип ключа.

*key*<br/>
Ключ элемента, который требуется удалить.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был найден и успешно удален; в противном случае 0.

### <a name="remarks"></a>Примечания

`DestructElements` Вспомогательная функция используется для удаления записи.

### <a name="example"></a>Пример

См. в примере [CMap::SetAt](#setat).

##  <a name="setat"></a>  CMap::SetAt

Основным средством для вставки элемента в сопоставлении.

```
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```

### <a name="parameters"></a>Параметры

*ARG_KEY*<br/>
Параметр шаблона, указывающий тип *ключ* параметра.

*key*<br/>
Задает ключ нового элемента.

*ARG_VALUE*<br/>
Параметр шаблона, указывающий тип *newValue* параметра.

*новое значение*<br/>
Указывает значение нового элемента.

### <a name="remarks"></a>Примечания

Во-первых ищется ключ. Если ключ найден, а затем соответствующее значение изменяется; в противном случае создается новую пару ключ значение.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../overview/visual-cpp-samples.md)<br/>
[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
