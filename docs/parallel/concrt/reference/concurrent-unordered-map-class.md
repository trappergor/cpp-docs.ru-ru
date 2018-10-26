---
title: Класс concurrent_unordered_map | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::at
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::unsafe_erase
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77198b9282dbf3def8a92d5a824f7fbeb313310f
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163443"
---
# <a name="concurrentunorderedmap-class"></a>Класс concurrent_unordered_map

Класс `concurrent_unordered_map` представляет собой безопасный в отношении параллелизма контейнер, управляющий последовательностью элементов типа `std::pair<const K, _Element_type>` переменной длины. Последовательность представлена таким образом, что позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора.

## <a name="syntax"></a>Синтаксис

```
template <typename K,
    typename _Element_type,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>
>,
typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>> class concurrent_unordered_map : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
details::_Hash_compare<K,
    _Hasher,
key_equality>,
    _Allocator_type,
false>>;
```

#### <a name="parameters"></a>Параметры

*K*<br/>
Тип ключа.

*_Element_type*<br/>
Сопоставленный тип.

*_Hasher*<br/>
Тип объекта хэш-функции. Этот аргумент является необязательным, и значением по умолчанию является `std::hash<K>`.

*key_equality*<br/>
Тип объекта функции сравнения на предмет равенства. Этот аргумент является необязательным, и значением по умолчанию является `std::equal_to<K>`.

*_Allocator_type*<br/>
Тип, представляющий сохраненный объект распределителя, инкапсулирующий сведения о выделении и освобождении памяти для параллельного не упорядоченного сопоставления. Этот аргумент является необязательным и значение по умолчанию — `std::allocator<std::pair<K`, `_Element_type>>`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`allocator_type`|Тип распределителя для управления хранилищем.|
|`const_iterator`|Тип постоянного итератора для управляемой последовательности.|
|`const_local_iterator`|Тип постоянного итератора блока для управляемой последовательности.|
|`const_pointer`|Тип постоянного указателя на элемент.|
|`const_reference`|Тип постоянной ссылки на элемент.|
|`difference_type`|Тип расстояния со знаком между двумя элементами.|
|`hasher`|Тип хэш-функции.|
|`iterator`|Тип итератора для управляемой последовательности.|
|`key_equal`|Тип функции сравнения.|
|`key_type`|Тип ключа упорядочения.|
|`local_iterator`|Тип итератора блока для управляемой последовательности.|
|`mapped_type`|Тип сопоставленного значения, связанного с каждым ключом.|
|`pointer`|Тип указателя на элемент.|
|`reference`|Тип ссылки на элемент.|
|`size_type`|Тип беззнакового расстояния между двумя элементами.|
|`value_type`|Тип элемента.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[concurrent_unordered_map](#ctor)|Перегружен. Создает параллельный не упорядоченный сопоставление.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[at](#at)|Перегружен. Находит элемент в `concurrent_unordered_map` с указанным значением ключа... Этот метод безопасен в режиме параллелизма.|
|[hash_function](#hash_function)|Получает сохраненный объект хэш-функции.|
|[insert](#insert)|Перегружен. Добавляет элементы `concurrent_unordered_map` объекта.|
|[key_eq](#key_eq)|Возвращает объект функции сравнения хранимых на равенство.|
|[swap](#swap)|Меняет местами содержимое двух `concurrent_unordered_map` объектов. Этот метод не является безопасным в режиме параллелизма.|
|[unsafe_erase](#unsafe_erase)|Перегружен. Удаляет элементы из `concurrent_unordered_map` в указанных позициях. Этот метод не является безопасным в режиме параллелизма.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор]](#operator_at)|Перегружен. Находит или вставляет элемент с указанным ключом. Этот метод безопасен в режиме параллелизма.|
|[оператор=](#operator_eq)|Перегружен. Назначает содержимое другого объекта `concurrent_unordered_map` в данный объект. Этот метод не является безопасным в режиме параллелизма.|

## <a name="remarks"></a>Примечания

Подробные сведения о `concurrent_unordered_map` , представлена в разделе [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_map`

## <a name="requirements"></a>Требования

**Заголовок:** concurrent_unordered_map.h

**Пространство имен:** concurrency

##  <a name="at"></a> в

Находит элемент в `concurrent_unordered_map` с указанным значением ключа... Этот метод безопасен в режиме параллелизма.

```
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*KVal*<br/>
Значение ключа, которое необходимо найти.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных найденного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, функция создает объект класса `out_of_range`.

##  <a name="begin"></a> начать

Возвращает итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на первый элемент в параллельном контейнере.

##  <a name="cbegin"></a> cbegin

Возвращает константный итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный итератор на первый элемент в параллельном контейнере.

##  <a name="cend"></a> cend

Возвращает константный итератор, указывающий на позицию после последнего элемента в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный итератор на позицию после последнего элемента в параллельном контейнере.

##  <a name="clear"></a> Очистить

Стирает все элементы в параллельном контейнере. Эта функция не безопасен в режиме параллелизма.

```
void clear();
```

##  <a name="ctor"></a> concurrent_unordered_map

Создает параллельный не упорядоченный сопоставление.

```
explicit concurrent_unordered_map(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_map(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap);

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_map(
    concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_Number_of_buckets*<br/>
Начальное количество сегментов для этого в неупорядоченном сопоставлении.

*_Hasher*<br/>
Хэш-функции для этого в неупорядоченном сопоставлении.

*key_equality*<br/>
Функция сравнения на равенство для этого в неупорядоченном сопоставлении.

*_Allocator*<br/>
Распределитель для этого в неупорядоченном сопоставлении.

*Н_ачать*<br/>
Положение первого элемента в диапазоне копируемых элементов.

*_Окончания*<br/>
Положение первого элемента после диапазона копируемых элементов.

*_Umap*<br/>
Исходный объект `concurrent_unordered_map` для копирования или перемещения элементов.

### <a name="remarks"></a>Примечания

Все конструкторы хранят объект распределителя `_Allocator` и инициализировать неупорядоченном сопоставлении.

Первый конструктор указывает пустое начальное сопоставление и явным образом указывает количество сегментов, хэш-функцию, функцию равенства и тип распределителя для использования.

Второй конструктор определяет распределитель для неупорядоченного карты.

Третий конструктор задает значения, передаваемые диапазоном итератора [ `_Begin`, `_End`).

Четвертый и пятый конструкторы определяют копию параллельного не упорядоченного сопоставления `_Umap`.

Последний конструктор определяет перемещение параллельного не упорядоченного сопоставления `_Umap`.

##  <a name="count"></a> число

Подсчитывает количество элементов, соответствующих заданному ключу. Эта функция является безопасен в режиме параллелизма.

```
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*KVal*<br/>
Ключ, который нужно найти.

### <a name="return-value"></a>Возвращаемое значение

Время количество появлений ключа в контейнере.

##  <a name="empty"></a> пустой

Проверяет отсутствие элементов. Данный метод безопасен в режиме параллелизма.

```
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** при параллельном контейнере пуст, **false** в противном случае.

### <a name="remarks"></a>Примечания

При наличии параллельных вставок пуст ли параллельном контейнере может измениться сразу же после вызова этой функции, прежде чем даже считывается возвращаемое значение.

##  <a name="end"></a> End

Возвращает итератор, указывающий на позицию после последнего элемента в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на позицию после последнего элемента в параллельном контейнере.

##  <a name="equal_range"></a> equal_range

Находит диапазон, соответствующий указанному ключу. Эта функция является безопасен в режиме параллелизма.

```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*KVal*<br/>
Значение ключа для поиска.

### <a name="return-value"></a>Возвращаемое значение

Объект [пары](../../../standard-library/pair-structure.md) где первый элемент — итератор, указывающий на начало, а второй элемент — итератор, указывающий конец диапазона.

### <a name="remarks"></a>Примечания

Параллельные операции вставки вызвать дополнительные ключи, вставляемый после начала итератора и перед конечный итератор возможна.

##  <a name="find"></a> найти

Определяет элемент, соответствующий указанному ключу. Эта функция является безопасен в режиме параллелизма.

```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*KVal*<br/>
Значение ключа для поиска.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на расположение первого элемента, с которым предоставленный ключ или итератор `end()` Если такого элемента не существует.

##  <a name="get_allocator"></a> get_allocator

Возвращает сохраненный объект распределителя для этом параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект распределителя для этом параллельном контейнере.

##  <a name="hash_function"></a> hash_function

Получает сохраненный объект хэш-функции.

```
hasher hash_function() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект хэш-функции.

##  <a name="insert"></a> Вставить

Добавляет элементы `concurrent_unordered_map` объекта.

```
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора, используемый для вставки.

*V*<br/>
Тип значения, вставляемого в схеме.

*значение*<br/>
Вставляемое значение.

*_Where*<br/>
Начальное положение для поиска точки вставки.

*Первый*<br/>
Начало диапазона, который необходимо вставить.

*последний*<br/>
Конец диапазона, который необходимо вставить.

### <a name="return-value"></a>Возвращаемое значение

Пару, которая содержит итератор, указывающий и логическое значение. См. Дополнительные сведения можно найти в разделе "Примечания".

### <a name="remarks"></a>Примечания

Первая функция-член определяет, существует ли в последовательности, ключ которого имеет соответствующий порядок, элемента X `value`. Если нет, он создает такой элемент X и инициализирует его с `value`. Функция затем определяет итератор `where` , обозначающий X. Если вставка произошла, функция возвращает `std::pair(where, true)`. В противном случае возвращает значение `std::pair(where, false)`.

Вторая функция-член возвращает insert ( `value`), с использованием `_Where` качестве отправной точки в управляемой последовательности для поиска точки вставки.

Третья функция-член вставляет последовательность значений элементов в диапазоне [ `first`, `last`).

Последние две функции-члена аналогичны первым двум, за исключением случаев, `value` используется для создания вставленное значение.

##  <a name="key_eq"></a> key_eq

Возвращает объект функции сравнения хранимых на равенство.

```
key_equal key_eq() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект функции сравнения хранимых на равенство.

##  <a name="load_factor"></a> load_factor

Вычисляет и возвращает текущий коэффициент нагрузки контейнера. Фактор нагрузки — количество элементов в контейнере, деленное на количество сегментов.

```
float load_factor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Коэффициент загрузки для контейнера.

##  <a name="max_load_factor"></a> max_load_factor

Возвращает или задает максимальный коэффициент нагрузки контейнера. Максимальный коэффициент нагрузки является наибольшее количество элементов, чем может быть в одном контейнере, прежде чем контейнера роста своей внутренней таблицы.

```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>Параметры

`_Newmax`

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция-член возвращает значение, но создает [out_of_range](../../../standard-library/out-of-range-class.md) исключение, если недопустимый фактор нагрузки...

##  <a name="max_size"></a> max_size

Возвращает максимальное число параллельных контейнеров, определяется распределителя. Данный метод безопасен в режиме параллелизма.

```
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество элементов, которые могут быть вставлены в этом параллельном контейнере.

### <a name="remarks"></a>Примечания

Это значение верхней границы фактически может быть выше, чем то, что еще фактически может содержаться в контейнере.

##  <a name="operator_at"></a> оператор]

Находит или вставляет элемент с указанным ключом. Этот метод безопасен в режиме параллелизма.

```
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```

### <a name="parameters"></a>Параметры

*KVal*<br/>
Значение ключа для

поиска или вставки.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на значение данных найденного или вставленного элемента.

### <a name="remarks"></a>Примечания

Если значение ключа аргумента не найдено, он вставляется вместе со значением по умолчанию для такого типа данных.

`operator[]` может использоваться для вставки элементов в сопоставление `m` с помощью `m[key] = DataValue;`, где `DataValue` — значение `mapped_type` элемента со значением ключа `key`.

При использовании `operator[]` для вставки элементов возвращаемая ссылка не отображает, меняет ли вставка уже существующий элемент или создает новый. Функции-члены `find` и [вставить](#insert) можно использовать для определения наличия элемента с указанным ключом перед вставкой.

##  <a name="operator_eq"></a> оператор =

Назначает содержимое другого объекта `concurrent_unordered_map` в данный объект. Этот метод не является безопасным в режиме параллелизма.

```
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>Параметры

*_Umap*<br/>
Исходный объект `concurrent_unordered_map`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `concurrent_unordered_map` объекта.

### <a name="remarks"></a>Примечания

После удаления всех существующих элементов в параллельном векторе `operator=` либо копирует, либо перемещает содержимое `_Umap` в параллельный вектор.

##  <a name="rehash"></a> rehash-

Повторно создает хэш-таблицу.

```
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>Параметры

*_Buckets*<br/>
Требуемое число сегментов.

### <a name="remarks"></a>Примечания

Функция-член устанавливает число сегментов не менее `_Buckets` и при необходимости перестраивает хэш-таблицу. Число контейнеров должно быть степенью числа 2. Если не является степенью числа 2, он будет округляться до следующего наибольшего степенью числа 2.

Он выдает [out_of_range](../../../standard-library/out-of-range-class.md) исключение, если число контейнеров, является недопустимым (0 или больше, чем максимальное число сегментов).

##  <a name="size"></a> Размер

Возвращает число элементов в этом параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в контейнере.

### <a name="remarks"></a>Примечания

При наличии параллельных вставок число элементов в параллельном контейнере может измениться сразу после вызова этой функции даже до чтения возвращаемого значения.

##  <a name="swap"></a> Swap

Меняет местами содержимое двух `concurrent_unordered_map` объектов. Этот метод не является безопасным в режиме параллелизма.

```
void swap(concurrent_unordered_map& _Umap);
```

### <a name="parameters"></a>Параметры

*_Umap*<br/>
Объект `concurrent_unordered_map` для обмена.

##  <a name="unsafe_begin"></a> unsafe_begin

Возвращает итератор, указывающий на первый элемент в этом контейнере для конкретного сегмента.

```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс сегмента.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало сегмента.

##  <a name="unsafe_bucket"></a> unsafe_bucket

Возвращает индекс сегмента, который сопоставляет указанный ключ в этом контейнере.

```
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*KVal*<br/>
Ключ элемента, которое требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Индекс сегмента ключа в этот контейнер.

##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count

Возвращает текущее количество сегментов в этом контейнере.

```
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее количество сегментов в этом контейнере.

##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size

Возвращает количество элементов из конкретного сегмента этого контейнера.

```
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Контейнер для поиска.

### <a name="return-value"></a>Возвращаемое значение

Текущее количество сегментов в этом контейнере.

##  <a name="unsafe_cbegin"></a> unsafe_cbegin

Возвращает итератор, указывающий на первый элемент в этом контейнере для конкретного сегмента.

```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс сегмента.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало сегмента.

##  <a name="unsafe_cend"></a> unsafe_cend

Возвращает итератор, указывающий на позицию после последнего элемента из конкретного сегмента.

```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс сегмента.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало сегмента.

##  <a name="unsafe_end"></a> unsafe_end

Возвращает итератор, указывающий на последний элемент в этом контейнере для конкретного сегмента.

```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс сегмента.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на конец сегмента.

##  <a name="unsafe_erase"></a> unsafe_erase

Удаляет элементы из `concurrent_unordered_map` в указанных позициях. Этот метод не является безопасным в режиме параллелизма.

```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator _Begin,
    const_iterator _End);

size_type unsafe_erase(
    const key_type& KVal);
```

### <a name="parameters"></a>Параметры

*_Where*<br/>
Положение итератора для удаления.

*Н_ачать*<br/>
Положение первого элемента в диапазоне элементов для удаления.

*_Окончания*<br/>
Положение первого элемента за пределами диапазона элементов для удаления.

*KVal*<br/>
Значение ключа для удаления.

### <a name="return-value"></a>Возвращаемое значение

Первые две функции-члена возвращают итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или `concurrent_unordered_map::end`(), если такой элемент не существует. Третья функция-член возвращает число элементов, которые она удаляет.

### <a name="remarks"></a>Примечания

Первая функция-член удаляет элемент управляемой последовательности, указанный параметром `_Where`. Вторая функция-член удаляет элементы в диапазоне [ `_Begin`, `_End`).

Третья функция-член удаляет элементы в диапазоне, ограниченном оболочкой `concurrent_unordered_map::equal_range`(KVal).

##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count

Возвращает максимальное число сегментов в этом контейнере.

```
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число сегментов в этом контейнере.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)

