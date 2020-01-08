---
title: Класс concurrent_unordered_multimap
ms.date: 11/04/2016
f1_keywords:
- concurrent_unordered_multimap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::concurrent_unordered_multimap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_multimap::unsafe_erase
helpviewer_keywords:
- concurrent_unordered_multimap class
ms.assetid: 4dada5d7-15df-4382-b9c9-348e75b2f3c1
ms.openlocfilehash: db4939d39c06a764ca73186e0be08ab4f8ecbcc1
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298601"
---
# <a name="concurrent_unordered_multimap-class"></a>Класс concurrent_unordered_multimap

Класс `concurrent_unordered_multimap` представляет собой безопасный в отношении параллелизма контейнер, управляющий последовательностью элементов типа `std::pair<const K, _Element_type>` переменной длины. Последовательность представлена таким образом, что позволяет параллельно-безопасно выполнять операции присоединения, получения доступа к элементу, доступа к итератору и обхода итератора. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода.

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
    _Element_type>>> class concurrent_unordered_multimap : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
details::_Hash_compare<K,
    _Hasher,
key_equality>,
    _Allocator_type,
true>>;
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
Тип, представляющий сохраненный объект распределителя, который инкапсулирует сведения о выделении и освобождении памяти для параллельного вектора. Этот аргумент является необязательным, и значение по умолчанию — `std::allocator<std::pair<K`, `_Element_type>>`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Открытые определения типов

|Name|Описание|
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

|Name|Описание|
|----------|-----------------|
|[concurrent_unordered_multimap](#ctor)|Перегружен. Создает параллельное неупорядоченное мультисопоставление.|

### <a name="public-methods"></a>Общедоступные методы

|Name|Описание|
|----------|-----------------|
|[hash_function](#hash_function)|Возвращает сохраненный объект хэш-функции.|
|[insert](#insert)|Перегружен. Добавляет элементы в объект `concurrent_unordered_multimap`.|
|[key_eq](#key_eq)|Возвращает сохраненный объект функции сравнения равенства.|
|[swap](#swap)|Меняет местами содержимое двух объектов `concurrent_unordered_multimap`. Этот метод не является типобезопасным в режиме параллелизма.|
|[unsafe_erase](#unsafe_erase)|Перегружен. Удаляет элементы из `concurrent_unordered_multimap` в указанных позициях. Этот метод не является типобезопасным в режиме параллелизма.|

### <a name="public-operators"></a>Открытые операторы

|Name|Описание|
|----------|-----------------|
|[operator=](#operator_eq)|Перегружен. Присваивает этому элементу содержимое другого объекта `concurrent_unordered_multimap`. Этот метод не является типобезопасным в режиме параллелизма.|

## <a name="remarks"></a>Заметки

Подробные сведения о классе `concurrent_unordered_multimap` см. в разделе [Parallel Containers and Objects](../../../parallel/concrt/parallel-containers-and-objects.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_multimap`

## <a name="requirements"></a>Требования

**Заголовок:** concurrent_unordered_map. h

**Пространство имен:** concurrency

##  <a name="begin"></a>начале

Возвращает итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор на первый элемент в параллельном контейнере.

##  <a name="cbegin"></a>cbegin

Возвращает константный итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный итератор для первого элемента в параллельном контейнере.

##  <a name="cend"></a>cend

Возвращает константный итератор, указывающий на расположение, следующее за последним элементом в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
const_iterator cend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Константный итератор к расположению, следующему за последним элементом в параллельном контейнере.

##  <a name="clear"></a>открытым

Стирает все элементы в параллельном контейнере. Эта функция не является типобезопасным.

```
void clear();
```

##  <a name="ctor"></a> concurrent_unordered_multimap

Создает параллельное неупорядоченное мультисопоставление.

```
explicit concurrent_unordered_multimap(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multimap(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_multimap(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multimap(
    const concurrent_unordered_multimap& _Umap);

concurrent_unordered_multimap(
    const concurrent_unordered_multimap& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_multimap(
    concurrent_unordered_multimap&& _Umap);
```

### <a name="parameters"></a>Параметры

*_Iterator*<br/>
Тип итератора ввода.

*_Number_of_buckets*<br/>
Начальное число блоков этого неупорядоченного мультисопоставления.

*_Hasher*<br/>
Хэш-функция для этого неупорядоченного мультисопоставления.

*key_equality*<br/>
Функция сравнения на равенство для этого неупорядоченного мультисопоставления.

*_Allocator*<br/>
Распределитель для этого неупорядоченного мультисопоставления.

*_Begin*<br/>
Положение первого элемента в диапазоне копируемых элементов.

*_End*<br/>
Положение первого элемента после диапазона копируемых элементов.

*_Umap*<br/>
Исходный объект `concurrent_unordered_multimap`, из которого копируются элементы.

### <a name="remarks"></a>Заметки

Все конструкторы содержат объект распределителя `_Allocator` и инициализируют неупорядоченное мультисопоставление.

Первый конструктор определяет изначально пустое мультисопоставление и явно задает число блоков, хэш-функцию, функцию равенства и тип распределителя, которые будут использоваться.

Второй конструктор определяет распределитель для неупорядоченного мультисопоставления.

Третий конструктор задает значения, предоставляемые диапазоном итератора [`_Begin`, `_End`).

Четвертый и пятый конструкторы определяют копию параллельного неупорядоченного мультисопоставления `_Umap`.

Последний конструктор определяет перемещение параллельного неупорядоченного мультисопоставления `_Umap`.

##  <a name="count"></a>расчета

Подсчитывает количество элементов, соответствующих указанному ключу. Эта функция является потенциальной в режиме параллелизма.

```
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомый ключ.

### <a name="return-value"></a>Возвращаемое значение

Количество раз, когда ключ отображается в контейнере.

##  <a name="empty"></a>указано

Проверяет отсутствие элементов. Данный метод безопасен в режиме параллелизма.

```
bool empty() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если параллельный контейнер пуст; в противном случае — **значение false** .

### <a name="remarks"></a>Заметки

При наличии параллельных вставок независимо от того, является ли параллельный контейнер пустым, может измениться сразу после вызова этой функции, прежде чем возвращаемое значение будет считаться четным.

##  <a name="end"></a>конце

Возвращает итератор, указывающий на расположение, следующее за последним элементом в параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор на расположение, на котором заканчивается последний элемент в параллельном контейнере.

##  <a name="equal_range"></a>equal_range

Находит диапазон, соответствующий указанному ключу. Эта функция является потенциальной в режиме параллелизма.

```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомое значение ключа.

### <a name="return-value"></a>Возвращаемое значение

[Пара](../../../standard-library/pair-structure.md) , в которой первый элемент является итератором на начало, а второй элемент — итератором на конец диапазона.

### <a name="remarks"></a>Заметки

Одновременные вставки могут привести к вставке дополнительных ключей после итератора begin и перед конечным итератором.

##  <a name="find"></a>Найдено

Определяет элемент, соответствующий указанному ключу. Эта функция является потенциальной в режиме параллелизма.

```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомое значение ключа.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на расположение первого элемента, совпадающего с предоставленным ключом, или итератор, `end()`, если такой элемент не существует.

##  <a name="get_allocator"></a>get_allocator

Возвращает сохраненный объект распределителя для этого параллельного контейнера. Данный метод безопасен в режиме параллелизма.

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект распределителя для этого параллельного контейнера.

##  <a name="hash_function"></a>hash_function

Возвращает сохраненный объект хэш-функции.

```
hasher hash_function() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект хэш-функции.

##  <a name="insert"></a>Вставляет

Добавляет элементы в объект `concurrent_unordered_multimap`.

```
iterator insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
iterator insert(
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
Тип значения, вставляемого в карту.

*значение*<br/>
Вставляемое значение.

*_Where*<br/>
Начальное расположение для поиска точки вставки.

*first*<br/>
Начало вставляемого диапазона.

*last*<br/>
Конец вставляемого диапазона.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на место вставки.

### <a name="remarks"></a>Заметки

Первая функция члена вставляет элемент `value` в управляемую последовательность, а затем возвращает итератор, который обозначает вставленный элемент.

Вторая функция-член возвращает инструкцию INSERT (`value`), используя `_Where` как начальную точку в управляемой последовательности для поиска точки вставки.

Третья функция-член вставляет последовательность значений элементов из диапазона [`first`, `last`).

Последние две функции-члена ведут себя так же, как первые два, за исключением того, что `value` используется для создания вставленного значения.

##  <a name="key_eq"></a>key_eq

Возвращает сохраненный объект функции сравнения равенства.

```
key_equal key_eq() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сохраненный объект функции сравнения равенства.

##  <a name="load_factor"></a>load_factor

Выполняет вычисление и возвращает текущий коэффициент загрузки контейнера. Коэффициент загрузки — это количество элементов в контейнере, деленное на количество сегментов.

```
float load_factor() const;
```

### <a name="return-value"></a>Возвращаемое значение

Коэффициент загрузки для контейнера.

##  <a name="max_load_factor"></a>max_load_factor

Возвращает или задает максимальный коэффициент загрузки контейнера. Максимальный коэффициент загрузки — это наибольшее число элементов, чем может быть в любом контейнере, прежде чем контейнер будет расти до размера внутренней таблицы.

```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>Параметры

`_Newmax`

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция-член не возвращает значение, но вызывает исключение [out_of_range](../../../standard-library/out-of-range-class.md) , если указанный коэффициент загрузки является недопустимым.

##  <a name="max_size"></a>max_size

Возвращает максимальный размер параллельного контейнера, определяемого распределителем. Данный метод безопасен в режиме параллелизма.

```
size_type max_size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число элементов, которые могут быть вставлены в этот параллельный контейнер.

### <a name="remarks"></a>Заметки

Это значение верхней границы может быть выше, чем на самом деле может храниться в контейнере.

##  <a name="operator_eq"></a>Оператор =

Присваивает этому элементу содержимое другого объекта `concurrent_unordered_multimap`. Этот метод не является типобезопасным в режиме параллелизма.

```
concurrent_unordered_multimap& operator= (const concurrent_unordered_multimap& _Umap);

concurrent_unordered_multimap& operator= (concurrent_unordered_multimap&& _Umap);
```

### <a name="parameters"></a>Параметры

*_Umap*<br/>
Исходный объект `concurrent_unordered_multimap`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `concurrent_unordered_multimap`.

### <a name="remarks"></a>Заметки

После удаления каких-либо существующих элементов из параллельного неупорядоченного контейнера multimap `operator=` либо копирует, либо перемещает содержимое `_Umap` в параллельный неупорядоченный контейнер multimap.

##  <a name="rehash"></a>rehash

Повторно создает хэш-таблицу.

```
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>Параметры

*_Buckets*<br/>
Необходимое количество сегментов.

### <a name="remarks"></a>Заметки

Функция-член устанавливает число сегментов не менее `_Buckets` и при необходимости перестраивает хэш-таблицу. Число сегментов должно быть степенью числа 2. Если не является степенью числа 2, она будет округляться до следующей самой крупной степени 2.

Он вызывает исключение [out_of_range](../../../standard-library/out-of-range-class.md) , если количество сегментов недопустимо (0 или больше максимального количества сегментов).

##  <a name="size"></a>изменять

Возвращает число элементов в этом параллельном контейнере. Данный метод безопасен в режиме параллелизма.

```
size_type size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число элементов в контейнере.

### <a name="remarks"></a>Заметки

При наличии параллельных вставок число элементов в параллельном контейнере может измениться сразу после вызова этой функции даже до чтения возвращаемого значения.

##  <a name="swap"></a>позиции

Меняет местами содержимое двух объектов `concurrent_unordered_multimap`. Этот метод не является типобезопасным в режиме параллелизма.

```
void swap(concurrent_unordered_multimap& _Umap);
```

### <a name="parameters"></a>Параметры

*_Umap*<br/>
Объект `concurrent_unordered_multimap` для обмена.

##  <a name="unsafe_begin"></a>unsafe_begin

Возвращает итератор, который является первым элементом в этом контейнере для определенного контейнера.

```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало контейнера.

##  <a name="unsafe_bucket"></a>unsafe_bucket

Возвращает индекс контейнера, сопоставляемый с указанным ключом в этом контейнере.

```
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>Параметры

*квал*<br/>
Искомый ключ элемента.

### <a name="return-value"></a>Возвращаемое значение

Индекс контейнера для ключа в этом контейнере.

##  <a name="unsafe_bucket_count"></a>unsafe_bucket_count

Возвращает текущее количество контейнеров в этом контейнере.

```
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Текущее число контейнеров в этом контейнере.

##  <a name="unsafe_bucket_size"></a>unsafe_bucket_size

Возвращает количество элементов в определенном контейнере этого контейнера.

```
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Контейнер для поиска.

### <a name="return-value"></a>Возвращаемое значение

Текущее число контейнеров в этом контейнере.

##  <a name="unsafe_cbegin"></a>unsafe_cbegin

Возвращает итератор, который является первым элементом в этом контейнере для определенного контейнера.

```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало контейнера.

##  <a name="unsafe_cend"></a>unsafe_cend

Возвращает итератор в позицию, которая завершилась после последнего элемента в определенном контейнере.

```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало контейнера.

##  <a name="unsafe_end"></a>unsafe_end

Возвращает итератор, который является последним элементом в этом контейнере для определенного контейнера.

```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>Параметры

*_Bucket*<br/>
Индекс контейнера.

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на конец контейнера.

##  <a name="unsafe_erase"></a>unsafe_erase

Удаляет элементы из `concurrent_unordered_multimap` в указанных позициях. Этот метод не является типобезопасным в режиме параллелизма.

```
iterator unsafe_erase(
    const_iterator _Where);

size_type unsafe_erase(
    const key_type& KVal);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>Параметры

*_Where*<br/>
Положение итератора для удаления.

*квал*<br/>
Значение ключа для удаления.

*first*<br/>
*last*<br/>
Итераторы.

### <a name="return-value"></a>Возвращаемое значение

Первые две функции-члена возвращают итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или `concurrent_unordered_multimap::end`(), если такой элемент не существует. Третья функция-член возвращает число элементов, которые она удаляет.

### <a name="remarks"></a>Заметки

Первая функция-член удаляет элемент управляемой последовательности, указанный параметром `_Where`. Вторая функция-член удаляет элементы в диапазоне [`_Begin`, `_End`).

Третья функция-член удаляет элементы в диапазоне, разделенном `concurrent_unordered_multimap::equal_range`(квал).

##  <a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count

Возвращает максимальное число контейнеров в этом контейнере.

```
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число контейнеров в этом контейнере.

## <a name="see-also"></a>См. также:

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)
