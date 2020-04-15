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
ms.openlocfilehash: 8a89ca7f7dedcd386abdd41e7487f1b838260c83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321442"
---
# <a name="catlmap-class"></a>Класс CAtlMap

Этот класс предоставляет методы создания и управления объектом карты.

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
Тип ключевого элемента.

*V*<br/>
Тип элемента значения.

*KTraits*<br/>
Код, используемый для копирования или перемещения ключевых элементов. Более подробную информацию можно узнать в [классе CElementTraits.](../../atl/reference/celementtraits-class.md)

*VTraits*<br/>
Код, используемый для копирования или перемещения элементов значения.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CAtlMap::KINARGTYPE](#kinargtype)|Тип, используемый при передаваемом ключе в качестве входиного аргумента|
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Введите используется при возврате ключа в качестве аргумента вывода.|
|[CAtlMap::VINARGTYPE](#vinargtype)|Тип используется при перевалке значения в качестве аргумента ввода.|
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Тип используется при перевалке значения в качестве аргумента вывода.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap::CPair Class](#cpair_class)|Класс, содержащий ключевые элементы и элементы значения.|

### <a name="cpair-data-members"></a>Члены CPair

|Имя|Описание|
|----------|-----------------|
|[CPair::m_key](#m_key)|Элемент данных, храпромевающих ключевой элемент.|
|[CPair::m_value](#m_value)|Элемент данных, храпромевающих элемент значения.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap::CAtlMap](#catlmap)|Конструктор.|
|[CAtlMap:::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap:AssertValid](#assertvalid)|Вызовите этот метод, `CAtlMap` чтобы вызвать ASSERT, если он недействителен.|
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Вызовите этот метод, чтобы отключить автоматическую перепев из `CAtlMap` объекта.|
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Вызовите этот метод, чтобы включить `CAtlMap` автоматическую перепев объекта.|
|[CAtlMap::GetAt](#getat)|Вызовите этот метод, чтобы вернуть элемент в указанном положении на карте.|
|[CAtlMap:GetCount](#getcount)|Вызовите этот метод, чтобы получить количество элементов на карте.|
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Вызовите этот метод, чтобы определить количество ячеек в таблице хэша карты.|
|[CAtlMap::GetKeyAt](#getkeyat)|Вызовите этот метод, чтобы получить ключ, `CAtlMap` хранящийся в заданном положении объекта.|
|[CAtlMap::GetNext](#getnext)|Вызовите этот метод, чтобы получить указатель `CAtlMap` на следующую пару элементов, хранящуюся в объекте.|
|[CAtlMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|
|[CAtlMap::GetNextKey](#getnextkey)|Вызовите этот метод, чтобы `CAtlMap` получить следующий ключ от объекта.|
|[CAtlMap::GetNextValue](#getnextvalue)|Вызовите этот метод, чтобы `CAtlMap` получить следующее значение от объекта.|
|[CAtlMap:GetStartPosition](#getstartposition)|Вызовите этот метод, чтобы начать итерацию карты.|
|[CAtlMap::GetvalueAt](#getvalueat)|Вызовите этот метод для получения значения, `CAtlMap` хранящегося в заданном положении объекта.|
|[CAtlMap::InitHashTable](#inithashtable)|Вызовите этот метод, чтобы инициализировать таблицу хэша.|
|[CAtlMap::IsEmpty](#isempty)|Вызовите этот метод для тестирования для пустого объекта карты.|
|[CAtlMap::Lookup](#lookup)|Вызовите этот метод, чтобы найти `CAtlMap` ключи или значения в объекте.|
|[CAtlMap::Rehash](#rehash)|Вызовите этот метод, `CAtlMap` чтобы переразить объект.|
|[CAtlMap::RemoveAll](#removeall)|Вызовите этот метод, `CAtlMap` чтобы удалить все элементы из объекта.|
|[CAtlMap::RemoveAtPos](#removeatpos)|Вызовите этот метод, чтобы удалить `CAtlMap` элемент в заданном положении объекта.|
|[CAtlMap::RemoveKey](#removekey)|Вызовите этот метод, `CAtlMap` чтобы удалить элемент из объекта, учитывая ключ.|
|[CAtlMap::SetAt](#setat)|Вызовите этот метод, чтобы вставить пару элементов в карту.|
|[CAtlMap::SetOptimalLoad](#setoptimalload)|Вызовите этот метод, чтобы `CAtlMap` установить оптимальную нагрузку объекта.|
|[CAtlMap::SetvalueAt](#setvalueat)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении `CAtlMap` объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Заменяет или добавляет новый `CAtlMap`элемент в .|

## <a name="remarks"></a>Remarks

`CAtlMap`обеспечивает поддержку массива карт любого данного типа, управляя неупорядоченным набором ключевых элементов и связанных с ними значений. Элементы (состоящие из ключа и значения) хранятся с помощью алгоритма хэширования, что позволяет эффективно хранить и извлекать большой объем данных.

Параметры *KTraits* и *VTraits* являются типами признаков, которые содержат любой дополнительный код, необходимый для копирования или перемещения элементов.

Альтернативу `CAtlMap` предлагает класс [CRBMap.](../../atl/reference/crbmap-class.md) `CRBMap`также хранит пары ключей/значений, но обладает различными характеристиками производительности. Время, заехаваемые на вставку элемента, поиск ключа или удаление ключа из `CRBMap` объекта, — это журнал заказов *(n),* где *n* — это число элементов. Для `CAtlMap`всех этих операций, как правило, занимает постоянное время, хотя наихудшие сценарии могут быть порядка *n.* Поэтому, в типичном `CAtlMap` случае, быстрее.

Другое различие `CRBMap` `CAtlMap` между и становится очевидным при итерации через сохраненные элементы. В `CRBMap`a, элементы посещаются в отсортированном порядке. В `CAtlMap`, элементы не заказываются, и не может быть выведен особой.

При необходимости хранения небольшого количества элементов следует использовать вместо этого класс [CSimpleMap.](../../atl/reference/csimplemap-class.md)

Для получения дополнительной информации, [см.](../../atl/atl-collection-classes.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>CAtlMap:AssertValid

Вызовите этот метод, `CAtlMap` чтобы вызвать ASSERT, если объект недействителен.

```
void AssertValid() const;
```

### <a name="remarks"></a>Remarks

В отладке сборки этот метод `CAtlMap` вызовет ASSERT, если объект недействителен.

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>CAtlMap::CAtlMap

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

*nБины*<br/>
Количество ячеек, обеспечивающих указатели на сохраненные элементы. Смотрите Замечания позже в этой теме для объяснения бункеров.

*fОптимальная нагрузка*<br/>
Оптимальное соотношение нагрузки.

*fLoThreshold*<br/>
Нижний порог соотношения нагрузки.

*fHiThreshold*<br/>
Верхний порог соотношения нагрузки.

*nBlockSize*<br/>
Размер блока.

### <a name="remarks"></a>Remarks

`CAtlMap`ссылается на все сохраненные элементы, сначала создав индекс с помощью алгоритма хэширования на ключе. Этот индекс ссылается на "бин", содержащий указатель на сохраненные элементы. Если ячейка уже используется, для доступа к последующим элементам создается связанный список. Обход списка происходит медленнее, чем прямой доступ к правильному элементу, и поэтому структура карты должна сбалансировать требования к хранению с производительностью. Параметры по умолчанию были выбраны, чтобы дать хорошие результаты в большинстве случаев.

Коэффициент нагрузки — это отношение количества ячеек к числу элементов, хранящихся в объекте карты. При пересчете структуры карты для расчета необходимого количества ячеек будет использоваться значение параметра *fOptimalLoad.* Это значение можно изменить с помощью метода [CAtlMap::SetOptimalLoad.](#setoptimalload)

Параметр *fLoThreshold* — это более низкое `CAtlMap` значение, которое соотношение нагрузки может достичь до пересчета оптимального размера карты.

Параметр *fHiThreshold* — это верхнее значение, `CAtlMap` которое может достичь соотношение нагрузки до того, как объект перессчитает оптимальный размер карты.

Этот процесс перерасчета (известный как перепев) включен по умолчанию. Если вы хотите отключить этот процесс, возможно, при вводе большого количества данных за один раз, позвоните в метод [CAtlMap::DisableAutoRehash.](#disableautorehash) Повторно активируйте его методом [CAtlMap::EnableAutoRehash.](#enableautorehash)

Параметр *nBlockSize* является мерой объема памяти, выделенного при необходимости нового элемента. Большие размеры блоков уменьшают вызовы для процедур распределения памяти, но используют больше ресурсов.

Прежде чем какие-либо данные могут быть сохранены, необходимо инициализировать хэш-таблицу с вызовом на [CAtlMap::InitHashTable](#inithashtable).

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>CAtlMap:::

Деструктор

```
~CAtlMap() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы.

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>CAtlMap::CPair Class

Класс, содержащий ключевые элементы и элементы значения.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Remarks

Этот класс используется методами [CAtlMap::GetNext](#getnext) и [CAtlMap::Lookup](#lookup) для доступа к элементам ключа и значений, хранящимся в структуре отображения.

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>CAtlMap::DisableAutoRehash

Вызовите этот метод, чтобы отключить автоматическую перепев из `CAtlMap` объекта.

```
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Remarks

При включении автоматического перепева (что по умолчанию) количество ячеек в таблице хэша автоматически пересчитывается, если значение нагрузки (отношение количества ячеек к числу элементов, хранящихся в массиве) превышает максимальное или минимальное значение, указанное на момент создания карты.

`DisableAutoRehash`наиболее полезно, когда на карту сразу будет добавлено большое количество элементов. Вместо того, чтобы запускать процесс перепева каждый раз, когда `DisableAutoRehash`пределы превышены, это более эффективно звонить, добавлять элементы, и, наконец, вызов [CAtlMap::EnableAutoRehash](#enableautorehash).

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>CAtlMap::EnableAutoRehash

Вызовите этот метод, чтобы включить `CAtlMap` автоматическую перепев объекта.

```
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Remarks

При включении автоматического перепева (что по умолчанию) количество ячеек в таблице хэша автоматически пересчитывается, если значение нагрузки (отношение количества ячеек к числу элементов, хранящихся в массиве) превышает максимальное или минимальное значение, указанное на момент создания карты.

`EnableAutoRefresh`чаще всего используется после звонка в [CAtlMap::D.A.AutoRehash](#disableautorehash).

## <a name="catlmapgetat"></a><a name="getat"></a>CAtlMap::GetAt

Вызовите этот метод, чтобы вернуть элемент в указанном положении на карте.

```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

*Ключ*<br/>
Параметры шаблона, определяющие тип ключа карты.

*value*<br/>
Параметры шаблона, определяющие тип значения карты.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на текущую пару элементов ключа/ценности, хранящихся на карте.

### <a name="remarks"></a>Remarks

В отладке сборки возникает ошибка утверждения, если *pos* равен NULL.

## <a name="catlmapgetcount"></a><a name="getcount"></a>CAtlMap:GetCount

Вызовите этот метод, чтобы получить количество элементов на карте.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов на объекте карты. Один элемент является парой ключей/значений.

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>CAtlMap::GetHashTableSize

Вызовите этот метод, чтобы определить количество ячеек в таблице хэша карты.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество ячеек в таблице хэша. Смотрите [CAtlMap::CAtlMap](#catlmap) для объяснения.

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>CAtlMap::GetKeyAt

Вызовите этот метод, чтобы получить ключ, `CAtlMap` хранящийся в заданном положении объекта.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на ключ, хранящийся в заданном положении `CAtlMap` объекта.

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapgetnext"></a><a name="getnext"></a>CAtlMap::GetNext

Вызовите этот метод, чтобы получить указатель `CAtlMap` на следующую пару элементов, хранящуюся в объекте.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель следующей паре элементов ключа/ценности, хранящихся на карте. Счетчик позиции *pos* обновляется после каждого вызова. Если извлеченный элемент является последним на карте, *pos* настроен на NULL.

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>CAtlMap::GetNextAssoc

Получает следующий элемент для итерации.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

*Ключ*<br/>
Параметры шаблона, определяющие тип ключа карты.

*value*<br/>
Параметры шаблона, определяющие тип значения карты.

### <a name="remarks"></a>Remarks

Счетчик позиции *pos* обновляется после каждого вызова. Если извлеченный элемент является последним на карте, *pos* настроен на NULL.

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>CAtlMap::GetNextKey

Вызовите этот метод, чтобы `CAtlMap` получить следующий ключ от объекта.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующий ключ на карте.

### <a name="remarks"></a>Remarks

Обновляет текущую позицию счетчик, *pos*. Если на карте больше нет записей, счетчик позиции устанавливается в NULL.

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>CAtlMap::GetNextValue

Вызовите этот метод, чтобы `CAtlMap` получить следующее значение от объекта.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на следующее значение на карте.

### <a name="remarks"></a>Remarks

Обновляет текущую позицию счетчик, *pos*. Если на карте больше нет записей, счетчик позиции устанавливается в NULL.

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>CAtlMap:GetStartPosition

Вызовите этот метод, чтобы начать итерацию карты.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает начальное положение или NULL возвращается, если карта пуста.

### <a name="remarks"></a>Remarks

Вызовите этот метод, чтобы начать итерацию карты, вернув значение POSITION, которое может быть передано методу. `GetNextAssoc`

> [!NOTE]
> Последовательность итерации не предсказуема

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>CAtlMap::GetvalueAt

Вызовите этот метод для получения значения, `CAtlMap` хранящегося в заданном положении объекта.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, хранящееся в данном положении `CAtlMap` объекта.

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>CAtlMap::InitHashTable

Вызовите этот метод, чтобы инициализировать таблицу хэша.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Параметры

*nБины*<br/>
Количество ячеек, используемых хэш-таблицей. Смотрите [CAtlMap::CAtlMap](#catlmap) для объяснения.

*bAllocNow*<br/>
Индикатор флага, когда память должна быть выделена.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE на успешную инициализацию, FALSE на провал.

### <a name="remarks"></a>Remarks

`InitHashTable`должны быть вызваны до того, как элементы будут храниться в таблице хэша.  Если этот метод не вызывается явно, он будет автоматически вызываться при первом добавлении элемента с помощью количества ячеек, указанного `CAtlMap` конструктором.  В противном случае карта будет инициализирована с использованием нового количества ячеек, указанного параметром *nBins.*

Если параметр *bAllocNow* является ложным, память, требуемая таблицей хэша, не будет выделена до тех пор, пока она не будет впервые необходима. Это может быть полезно, если неизвестно, будет ли использоваться карта.

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapisempty"></a><a name="isempty"></a>CAtlMap::IsEmpty

Вызовите этот метод для тестирования для пустого объекта карты.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если карта пуста, FALSE в противном случае.

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>CAtlMap::KINARGTYPE

Тип используется при передаваемом ключе в качестве входиного аргумента.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>CAtlMap::KOUTARGTYPE

Введите используется при возврате ключа в качестве аргумента вывода.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>CAtlMap::Lookup

Вызовите этот метод, чтобы найти `CAtlMap` ключи или значения в объекте.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Определяет ключ, который определяет элемент, который следует изыскнуть.

*value*<br/>
Переменная, которая получает значение "загнан".

### <a name="return-value"></a>Возвращаемое значение

Первая форма метода возвращается верно, если ключ найден, в противном случае ложно. Вторая и третья формы возвращают указатель в [CPair,](#cpair_class) который может быть использован в качестве позиции для звонков в [CAtlMap::GetNext](#getnext) и так далее.

### <a name="remarks"></a>Remarks

`Lookup`использует алгоритм хэширования, чтобы быстро найти элемент карты, содержащий ключ, который точно соответствует заданного ключевого параметра.

## <a name="catlmapoperator-"></a><a name="operator_at"></a>CAtlMap:оператор\[\]

Заменяет или добавляет новый `CAtlMap`элемент в .

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ элемента для добавления или замены.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на значение, связанное с данным ключом.

### <a name="example"></a>Пример

Если ключ уже существует, элемент заменяется. Если ключ не существует, добавляется новый элемент. Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmaprehash"></a><a name="rehash"></a>CAtlMap::Rehash

Вызовите этот метод, `CAtlMap` чтобы переразить объект.

```
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Параметры

*nБины*<br/>
Новое количество ячеек для использования в таблице хэша. Смотрите [CAtlMap::CAtlMap](#catlmap) для объяснения.

### <a name="remarks"></a>Remarks

Если *nBins* равен 0, `CAtlMap` вычисляет разумное число на основе количества элементов на карте и оптимальной настройки нагрузки. Обычно процесс перепева происходит автоматически, но если [cAtlMap::DisableAutoRehash](#disableautorehash) был вызван, этот метод будет выполнять необходимые изменение размера.

## <a name="catlmapremoveall"></a><a name="removeall"></a>CAtlMap::RemoveAll

Вызовите этот метод, `CAtlMap` чтобы удалить все элементы из объекта.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Remarks

Очищает `CAtlMap` объект, освобождая память, используемую для хранения элементов.

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>CAtlMap::RemoveAtPos

Вызовите этот метод, чтобы удалить `CAtlMap` элемент в заданном положении объекта.

```
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

### <a name="remarks"></a>Remarks

Удаляет пару ключей/значений, хранящуюся в указанном положении. Память, используемая для хранения элемента, освобождается. POSITION, на который ссылается *pos,* становится недействительным, и хотя POSITION любых других элементов на карте остается действительным, они не обязательно сохраняют тот же порядок.

## <a name="catlmapremovekey"></a><a name="removekey"></a>CAtlMap::RemoveKey

Вызовите этот метод, `CAtlMap` чтобы удалить элемент из объекта, учитывая ключ.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключ, соответствующий паре элементов, который вы хотите удалить.

### <a name="return-value"></a>Возвращаемое значение

Возвращает TRUE, если ключ найден и удален, FALSE на сбой.

### <a name="example"></a>Пример

Смотрите пример [CAtlMap::CAtlMap](#catlmap).

## <a name="catlmapsetat"></a><a name="setat"></a>CAtlMap::SetAt

Вызовите этот метод, чтобы вставить пару элементов в карту.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*Ключ*<br/>
Ключевое значение для `CAtlMap` добавления к объекту.

*value*<br/>
Значение для добавления к объекту. `CAtlMap`

### <a name="return-value"></a>Возвращаемое значение

Возвращает положение пары элементов ключа/значения `CAtlMap` в объекте.

### <a name="remarks"></a>Remarks

`SetAt`заменяет существующий элемент при обнаружении соответствующего ключа. Если ключ не найден, создается новая пара ключей/значений.

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>CAtlMap::SetOptimalLoad

Вызовите этот метод, чтобы `CAtlMap` установить оптимальную нагрузку объекта.

```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Параметры

*fОптимальная нагрузка*<br/>
Оптимальное соотношение нагрузки.

*fLoThreshold*<br/>
Нижний порог соотношения нагрузки.

*fHiThreshold*<br/>
Верхний порог соотношения нагрузки.

*bRehashТеперь*<br/>
Пометить, следует ли перессчитать таблицу хэша.

### <a name="remarks"></a>Remarks

Этот метод переопределяет оптимальное `CAtlMap` значение нагрузки для объекта. Смотрите [CAtlMap::CAtlMap](#catlmap) для обсуждения различных параметров. Если *bRehashNow* истинен, а количество элементов находится за пределами минимальных и максимальных значений, таблица хэша пересчитывается.

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>CAtlMap::SetvalueAt

Вызовите этот метод, чтобы изменить значение, хранящееся в заданном положении `CAtlMap` объекта.

```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Параметры

*pos*<br/>
Счетчик позиции, возвращенный предыдущим вызовом в [CAtlMap::GetNextAssoc](#getnextassoc) или [CAtlMap::GetStartPosition](#getstartposition).

*value*<br/>
Значение для добавления к объекту. `CAtlMap`

### <a name="remarks"></a>Remarks

Изменяет элемент значения, хранящийся в заданном положении `CAtlMap` объекта.

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>CAtlMap::VINARGTYPE

Тип используется при перевалке значения в качестве аргумента ввода.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>CAtlMap::VOUTARGTYPE

Тип используется при перевалке значения в качестве аргумента вывода.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>CAtlMap::CPair::m_key

Элемент данных, храпромевающих ключевой элемент.

```
const K m_key;
```

### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключевого элемента.

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>CAtlMap::CPair::m_value

Элемент данных, храпромевающих элемент значения.

```
V  m_value;
```

### <a name="parameters"></a>Параметры

*V*<br/>
Тип элемента значения.

## <a name="see-also"></a>См. также раздел

[Маркес](../../overview/visual-cpp-samples.md)<br/>
[Образец UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
