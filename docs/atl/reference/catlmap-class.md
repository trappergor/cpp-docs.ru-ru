---
title: Класс CAtlMap
ms.date: 11/04/2016
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: 80975047b300f270c0ac58c8b8abfc59ff2b17ef
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293788"
---
# <a name="catlmap-class"></a>Класс CAtlMap

Этот класс предоставляет методы для создания и управления объект карты.

## <a name="syntax"></a>Синтаксис

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа элемента.

*V*<br/>
Тип значения элемента.

*KTraits*<br/>
Код, используемый для копирования или перемещения ключевые элементы. См. в разделе [класс CElementTraits](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.

*VTraits*<br/>
Код, используемый для копирования или перемещения элементов value.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|[CAtlMap::KINARGTYPE](#kinargtype)|Тип, используемый при передаче ключа в качестве входного аргумента|
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Тип, используемый при возврате ключа в виде выходного аргумента.|
|[CAtlMap::VINARGTYPE](#vinargtype)|Тип, используемый, когда значение передается в качестве входного аргумента.|
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Тип, используемый, когда значение передается в качестве выходного аргумента.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание:|
|----------|-----------------|
|[Класс CAtlMap::CPair](#cpair_class)|Класс, содержащий элементы ключ и значение.|

### <a name="cpair-data-members"></a>CPair данные-члены

|name|Описание|
|----------|-----------------|
|[CPair::m_key](#m_key)|Элемент данных, хранения ключа элемента.|
|[CPair::m_value](#m_value)|Элемент данных, хранения значение элемента.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CAtlMap::CAtlMap](#catlmap)|Конструктор.|
|[CAtlMap:: ~ CAtlMap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap::AssertValid](#assertvalid)|Вызовите этот метод, чтобы вызвать метод ASSERT, если `CAtlMap` является недопустимым.|
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Вызовите этот метод, чтобы отключить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.|
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Вызовите этот метод, чтобы включить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.|
|[CAtlMap::GetAt](#getat)|Этот метод используется для возвращения элемента в указанной позиции на карте.|
|[CAtlMap::GetCount](#getcount)|Вызовите этот метод для получения числа элементов в сопоставлении.|
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Этот метод используется для определения количества ячеек в карты хэш-таблице.|
|[CAtlMap::GetKeyAt](#getkeyat)|Вызовите этот метод для извлечения ключа, хранящегося в заданной позиции в `CAtlMap` объекта.|
|[CAtlMap::GetNext](#getnext)|Вызовите этот метод, чтобы получить указатель на следующий элемент, пара хранится в `CAtlMap` объекта.|
|[CAtlMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|
|[CAtlMap::GetNextKey](#getnextkey)|Вызовите этот метод для получения следующего ключа из `CAtlMap` объекта.|
|[CAtlMap::GetNextValue](#getnextvalue)|Вызовите этот метод для получения следующего значения из `CAtlMap` объекта.|
|[CAtlMap::GetStartPosition](#getstartposition)|Вызовите этот метод перед началом итерации карты.|
|[CAtlMap::GetValueAt](#getvalueat)|Вызовите этот метод, чтобы извлечь значение, сохраненное в заданном положении в `CAtlMap` объекта.|
|[CAtlMap::InitHashTable](#inithashtable)|Вызовите этот метод для инициализации хэш-таблице.|
|[CAtlMap::IsEmpty](#isempty)|Этот метод используется для проверки объекта пустое сопоставление.|
|[CAtlMap::Lookup](#lookup)|Вызовите этот метод для поиска ключей и значений в `CAtlMap` объекта.|
|[CAtlMap::Rehash](#rehash)|Вызовите этот метод для rehash- `CAtlMap` объекта.|
|[CAtlMap::RemoveAll](#removeall)|Вызовите этот метод для удаления всех элементов из `CAtlMap` объекта.|
|[CAtlMap::RemoveAtPos](#removeatpos)|Вызовите этот метод для удаления элемента в заданной позиции в `CAtlMap` объекта.|
|[CAtlMap::RemoveKey](#removekey)|Вызовите этот метод для удаления элемента из `CAtlMap` объекту, заданному ключу.|
|[CAtlMap::SetAt](#setat)|Этот метод используется для вставки пары элементов в сопоставление.|
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Вызовите этот метод для установки оптимального нагрузку `CAtlMap` объекта.|
|[CAtlMap::SetValueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CAtlMap` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Заменяет или добавляет новый элемент к `CAtlMap`.|

## <a name="remarks"></a>Примечания

`CAtlMap` предоставляет поддержку для сопоставления массива заданного типа, управление массив неупорядоченные ключевые элементы и связанные с ними значения. Элементы (состоящей из ключа и значения) хранятся с использованием алгоритма хэширования, позволяя большой объем данных, эффективно хранить и получить.

*KTraits* и *VTraits* параметры являются traits-классы, содержащие любой дополнительный код, необходимый для копирования или перемещения элементов.

Альтернативой `CAtlMap` предложенного [CRBMap](../../atl/reference/crbmap-class.md) класса. `CRBMap` также хранит пары "ключ значение", но существуют разные характеристики производительности. Время, необходимое для вставки элемента, поиска ключа или удаления ключа из `CRBMap` объект является заказа *log(n)*, где *n* — количество элементов. Для `CAtlMap`, все эти операции обычно принимают константном времени, несмотря на то, что модели наихудших возможных ситуаций может быть заказа *n*. Таким образом, в обычной ситуации `CAtlMap` выполняется быстрее.

Других различий между `CRBMap` и `CAtlMap` становится очевидным, когда перебора хранимых элементов. В `CRBMap`, которые вы посещаете элементов в отсортированном порядке. В `CAtlMap`, элементы не упорядочены и порядок не могут быть заданы.

При необходимости храниться небольшое количество элементов, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класса.

Дополнительные сведения см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="assertvalid"></a>  CAtlMap::AssertValid

Вызовите этот метод, чтобы вызвать метод ASSERT, если `CAtlMap` объект не является допустимым.

```
void AssertValid() const;
```

### <a name="remarks"></a>Примечания

В отладочных сборках, этот метод будет вызывать ASSERT, если `CAtlMap` объект не является допустимым.

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="catlmap"></a>  CAtlMap::CAtlMap

Конструктор.

```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>Параметры

*nBins*<br/>
Количество ячеек, предоставляя указатели хранимых элементы. См. в разделе "Примечания" Далее в этом разделе объяснение ячейки.

*fOptimalLoad*<br/>
Отношение оптимальной нагрузки.

*fLoThreshold*<br/>
Нижнее пороговое значение коэффициента нагрузки.

*fHiThreshold*<br/>
Верхнее пороговое значение коэффициента нагрузки.

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Примечания

`CAtlMap` ссылается на все хранимые элементов путем первоначального создания индекса с помощью хэш-алгоритма по ключу. Этот индекс ссылается на «bin», который содержит указатель на хранимые элементы. Если ячейка уже используется, в связанном списке создается для доступа к последующим элементам. Обход списка выполняется медленнее, чем прямой доступ к правильный элемент, и поэтому структуре карты необходимо сбалансировать требования к хранилищу с производительностью. Параметры по умолчанию были выбраны для предоставления хорошие результаты в большинстве случаев.

Коэффициент нагрузки — это отношение числа ячеек на количество элементов, хранящихся в объекте map. При пересчете структуре карты *fOptimalLoad* значение параметра будет использоваться для вычисления числа ячеек, которые требуется. Это значение можно изменить с помощью [CAtlMap::SetOptimalLoad](#setoptimalload) метод.

*FLoThreshold* параметр имеет меньшее значение, которое коэффициент нагрузки, при достижении `CAtlMap` приведет к пересчету оптимальный размер объекта map.

*FHiThreshold* параметром является значение верхней, коэффициент нагрузки, при достижении `CAtlMap` объект будет повторно вычислить оптимальный размер объекта map.

Этот процесс повторного вычисления (известный как проведя пересчет контрольной суммы) включен по умолчанию. Если вы хотите отключить этот процесс, возможно, при вводе большой объем данных за один раз вызов [CAtlMap::DisableAutoRehash](#disableautorehash) метод. Повторно активировать ее с [CAtlMap::EnableAutoRehash](#enableautorehash) метод.

*NBlockSize* параметр — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов.

Прежде чем могут храниться любые данные, это необходимо для инициализации хэш-таблицы с помощью вызова [CAtlMap::InitHashTable](#inithashtable).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

##  <a name="dtor"></a>  CAtlMap:: ~ CAtlMap

Деструктор

```
~CAtlMap() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="cpair_class"></a>  Класс CAtlMap::CPair

Класс, содержащий элементы ключ и значение.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Примечания

Этот класс используется методами [CAtlMap::GetNext](#getnext) и [CAtlMap::Lookup](#lookup) для доступа к элементам ключа и значения, хранящиеся в структуре сопоставления.

##  <a name="disableautorehash"></a>  CAtlMap::DisableAutoRehash

Вызовите этот метод, чтобы отключить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.

```
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Примечания

Если автоматическое проведя пересчет контрольной суммы включено (который по умолчанию он разрешен), число ячеек в хэш-таблице пересчитывается автоматически превышения нагрузки значение (соотношение числа ячеек на количество элементов, которые хранятся в массиве) максимальных или минимальных значений указан во время создания карты.

`DisableAutoRehash` может пригодиться, когда большое количество элементов будут добавлены на карту за один раз. Вместо вызывающей срабатывание rehashing процесса, каждый раз при превышении ограничений, эффективнее вызывать `DisableAutoRehash`, добавьте элементы и вызвать [CAtlMap::EnableAutoRehash](#enableautorehash).

##  <a name="enableautorehash"></a>  CAtlMap::EnableAutoRehash

Вызовите этот метод, чтобы включить автоматическое проведя пересчет контрольной суммы из `CAtlMap` объекта.

```
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Примечания

Если автоматическое проведя пересчет контрольной суммы включено (который по умолчанию он разрешен), число ячеек в хэш-таблице пересчитывается автоматически превышения нагрузки значение (соотношение числа ячеек на количество элементов, которые хранятся в массиве) максимальных или минимальных значений указан во время создания карты.

`EnableAutoRefresh` Чаще всего используется после вызова [CAtlMap::DisableAutoRehash](#disableautorehash).

##  <a name="getat"></a>  CAtlMap::GetAt

Этот метод используется для возвращения элемента в указанной позиции на карте.

```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

*key*<br/>
Параметр шаблона, указывающий тип ключа карты.

*value*<br/>
Параметр шаблона, указывающий тип значения карты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на текущей паре ключ значение элементов, сохраненную в сопоставлении.

### <a name="remarks"></a>Примечания

В отладочных сборках, произойдет ошибка утверждения, если *pos* равен NULL.

##  <a name="getcount"></a>  CAtlMap::GetCount

Вызовите этот метод для получения числа элементов в сопоставлении.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число элементов в объекте map. Один элемент является парой ключ/значение.

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="gethashtablesize"></a>  CAtlMap::GetHashTableSize

Этот метод используется для определения количества ячеек в карты хэш-таблице.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество ячеек в хэш-таблице. См. в разделе [CAtlMap::CAtlMap](#catlmap) объяснение.

##  <a name="getkeyat"></a>  CAtlMap::GetKeyAt

Вызовите этот метод для извлечения ключа, хранящегося в заданной позиции в `CAtlMap` объекта.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на ключ, хранящийся в заданной позиции в `CAtlMap` объекта.

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="getnext"></a>  CAtlMap::GetNext

Вызовите этот метод, чтобы получить указатель на следующий элемент, пара хранится в `CAtlMap` объекта.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на следующая пара ключ/значение элементов, содержащихся в схеме. *Pos* позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в схеме, *pos* имеет значение NULL.

##  <a name="getnextassoc"></a>  CAtlMap::GetNextAssoc

Получает следующий элемент для выполнения итерации.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

*key*<br/>
Параметр шаблона, указывающий тип ключа карты.

*value*<br/>
Параметр шаблона, указывающий тип значения карты.

### <a name="remarks"></a>Примечания

*Pos* позиции счетчик обновляется после каждого вызова. Если полученный элемент является последним в схеме, *pos* имеет значение NULL.

##  <a name="getnextkey"></a>  CAtlMap::GetNextKey

Вызовите этот метод для получения следующего ключа из `CAtlMap` объекта.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующий ключ в сопоставлении.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиции, *pos*. Если нет дополнительных записей в сопоставлении, счетчик позиции присваивается значение NULL.

##  <a name="getnextvalue"></a>  CAtlMap::GetNextValue

Вызовите этот метод для получения следующего значения из `CAtlMap` объекта.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующее значение в сопоставлении.

### <a name="remarks"></a>Примечания

Обновляет текущий счетчик позиции, *pos*. Если нет дополнительных записей в сопоставлении, счетчик позиции присваивается значение NULL.

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="getstartposition"></a>  CAtlMap::GetStartPosition

Вызовите этот метод перед началом итерации карты.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает начальное положение, или значение NULL возвращается, если сопоставление является пустым.

### <a name="remarks"></a>Примечания

Вызов, этот метод для запуска итерации карты, возвращая ПОЗИЦИЮ значение, которое может быть передан `GetNextAssoc` метод.

> [!NOTE]
>  В последовательности итерации не является прогнозируемым

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="getvalueat"></a>  CAtlMap::GetValueAt

Вызовите этот метод, чтобы извлечь значение, сохраненное в заданном положении в `CAtlMap` объекта.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, хранящееся в заданном положении в `CAtlMap` объекта.

##  <a name="inithashtable"></a>  CAtlMap::InitHashTable

Вызовите этот метод для инициализации хэш-таблице.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Параметры

*nBins*<br/>
Количество ячеек, используемых хэш-таблице. См. в разделе [CAtlMap::CAtlMap](#catlmap) объяснение.

*bAllocNow*<br/>
Флаг указывает, когда памяти необходимо выделить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE при успешной инициализации FALSE в случае сбоя.

### <a name="remarks"></a>Примечания

`InitHashTable` должен вызываться, прежде чем какие-либо элементы хранятся в хэш-таблице.  Если этот метод не вызывается явным образом, он будет вызываться автоматически при первом добавлении элемента с помощью число ячеек, определяемое `CAtlMap` конструктор.  В противном случае карты будет инициализирован с помощью нового число ячеек, определяемое *nBins* параметра.

Если *bAllocNow* параметр имеет значение false, пока это сначала требуется не будет выделена память, необходимую хэш-таблице. Это может быть полезно в том случае, если непонятно, будет ли использоваться карты.

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="isempty"></a>  CAtlMap::IsEmpty

Этот метод используется для проверки объекта пустое сопоставление.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если сопоставление является пустым, значение FALSE в противном случае.

##  <a name="kinargtype"></a>  CAtlMap::KINARGTYPE

Тип, используемый при передаче ключа в качестве входного аргумента.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CAtlMap::KOUTARGTYPE

Тип, используемый при возврате ключа в виде выходного аргумента.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="lookup"></a>  CAtlMap::Lookup

Вызовите этот метод для поиска ключей и значений в `CAtlMap` объекта.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Задает ключ, определяющий элемент, выполняется поиск.

*value*<br/>
Переменная, которая получает искомого значения.

### <a name="return-value"></a>Возвращаемое значение

В первой форме метода возвращает значение true, если ключ найден, в противном случае — значение false. Второй и третьей форме возвращают указатель на [CPair](#cpair_class) которого может использоваться в качестве позиции для вызовов [CAtlMap::GetNext](#getnext) и т. д.

### <a name="remarks"></a>Примечания

`Lookup` использует алгоритм хэширования для быстрого поиска элемента карты, содержащего ключ, которая точно совпадает с заданным параметром ключа.

##  <a name="operator_at"></a>  CAtlMap::operator \[\]

Заменяет или добавляет новый элемент к `CAtlMap`.

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ элемента для добавления или замены.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, связанное с указанным ключом.

### <a name="example"></a>Пример

Если ключ уже существует, заменяется элемент. Если ключ не существует, добавляется новый элемент. См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="rehash"></a>  CAtlMap::Rehash

Вызовите этот метод для rehash- `CAtlMap` объекта.

```
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Параметры

*nBins*<br/>
Новое число ячеек для использования в хэш-таблице. См. в разделе [CAtlMap::CAtlMap](#catlmap) объяснение.

### <a name="remarks"></a>Примечания

Если *nBins* равно 0, `CAtlMap` вычисляет разумные количества зависимости от числа элементов в сопоставлении и параметр оптимальной нагрузки. Обычно rehashing процесс происходит автоматически, но если [CAtlMap::DisableAutoRehash](#disableautorehash) был вызван, этот метод будет выполнять необходимые изменения размера.

##  <a name="removeall"></a>  CAtlMap::RemoveAll

Вызовите этот метод для удаления всех элементов из `CAtlMap` объекта.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Примечания

Очищает `CAtlMap` объект, память, используемую для хранения элементов.

##  <a name="removeatpos"></a>  CAtlMap::RemoveAtPos

Вызовите этот метод для удаления элемента в заданной позиции в `CAtlMap` объекта.

```
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="remarks"></a>Примечания

Удаляет пару ключ значение, хранящееся в указанной позиции. Освобождается память, используемая для сохранения элемента. ПОЗИЦИЯ ссылается *pos* становится недействительным, а в то время как положение любых других элементов в сопоставлении остается допустимым, это не обязательно хранить в том же порядке.

##  <a name="removekey"></a>  CAtlMap::RemoveKey

Вызовите этот метод для удаления элемента из `CAtlMap` объекту, заданному ключу.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, соответствующий пары элементов действительно необходимо удалить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если ключ найден и удален, и FALSE в случае сбоя.

### <a name="example"></a>Пример

См. в примере [CAtlMap::CAtlMap](#catlmap).

##  <a name="setat"></a>  CAtlMap::SetAt

Этот метод используется для вставки пары элементов в сопоставление.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Значение ключа, чтобы добавить `CAtlMap` объекта.

*value*<br/>
Значение, которое нужно добавить `CAtlMap` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию элемента пары ключ/значение в `CAtlMap` объекта.

### <a name="remarks"></a>Примечания

`SetAt` заменяет существующий элемент, если найден соответствующий ключ. Если ключ не найден, создается новую пару ключ значение.

##  <a name="setoptimalload"></a>  CAtlMap::SetOptimalLoad

Вызовите этот метод для установки оптимального нагрузку `CAtlMap` объекта.

```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Параметры

*fOptimalLoad*<br/>
Отношение оптимальной нагрузки.

*fLoThreshold*<br/>
Нижнее пороговое значение коэффициента нагрузки.

*fHiThreshold*<br/>
Верхнее пороговое значение коэффициента нагрузки.

*bRehashNow*<br/>
Флаг, указывающий, если хэш-таблицы должны быть пересчитаны.

### <a name="remarks"></a>Примечания

Этот метод переопределяет значение оптимальной нагрузки `CAtlMap` объекта. См. в разделе [CAtlMap::CAtlMap](#catlmap) обсуждение различных параметров. Если *bRehashNow* имеет значение true и число элементов, которое находится за пределами минимальное и максимальное значения, вычисляется хэш-таблице.

##  <a name="setvalueat"></a>  CAtlMap::SetValueAt

Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении в `CAtlMap` объекта.

```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
Счетчик позиции, возвращенный предыдущим вызовом [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

*value*<br/>
Значение, которое нужно добавить `CAtlMap` объекта.

### <a name="remarks"></a>Примечания

Изменяет значение элемента, хранящихся в заданной позиции в `CAtlMap` объекта.

##  <a name="vinargtype"></a>  CAtlMap::VINARGTYPE

Тип, используемый, когда значение передается в качестве входного аргумента.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CAtlMap::VOUTARGTYPE

Тип, используемый, когда значение передается в качестве выходного аргумента.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

##  <a name="m_key"></a>  CAtlMap::CPair::m_key

Элемент данных, хранения ключа элемента.

```
const K m_key;
```

### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа элемента.

##  <a name="m_value"></a>  CAtlMap::CPair::m_value

Элемент данных, хранения значение элемента.

```
V  m_value;
```

### <a name="parameters"></a>Параметры

*V*<br/>
Тип значения элемента.

## <a name="see-also"></a>См. также

[Пример бегущей строки](../../visual-cpp-samples.md)<br/>
[Образец UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
