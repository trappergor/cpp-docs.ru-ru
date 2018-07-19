---
title: Класс concurrent_unordered_map | Документы Microsoft
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
ms.openlocfilehash: 932cfe232b07a9020af450ad33bb34101827ac79
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695533"
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
 `K`  
 Тип ключа.  
  
 `_Element_type`  
 Сопоставленный тип.  
  
 `_Hasher`  
 Тип объекта хэш-функции. Этот аргумент является необязательным, и значением по умолчанию является `std::hash<K>`.  
  
 `key_equality`  
 Тип объекта функции сравнения на предмет равенства. Этот аргумент является необязательным, и значением по умолчанию является `std::equal_to<K>`.  
  
 `_Allocator_type`  
 Тип, представляющий сохраненный объект распределителя, инкапсулирующий сведения о выделении и освобождении памяти для параллельных неупорядоченном сопоставлении. Этот аргумент является необязательным, и значение по умолчанию — `std::allocator<std::pair<K`, `_Element_type>>`.  
  
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
|[concurrent_unordered_map](#ctor)|Перегружен. Создает параллельный неупорядоченном сопоставлении.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[at](#at)|Перегружен. Находит элемент в `concurrent_unordered_map` с заданным значением ключа... Данный метод безопасен в режиме параллелизма.|  
|[hash_function](#hash_function)|Получает сохраненный объект хэш-функции.|  
|[insert](#insert)|Перегружен. Добавляет элементы к `concurrent_unordered_map` объекта.|  
|[key_eq](#key_eq)|Возвращает объект функции сравнения хранимых равенства.|  
|[swap](#swap)|Меняет местами содержимое двух `concurrent_unordered_map` объектов. Этот метод не является безопасным в режиме параллелизма.|  
|[unsafe_erase](#unsafe_erase)|Перегружен. Удаляет элементы из `concurrent_unordered_map` в указанных позициях. Этот метод не является безопасным в режиме параллелизма.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор]](#operator_at)|Перегружен. Находит или вставляет элемент с указанным ключом. Данный метод безопасен в режиме параллелизма.|  
|[оператор=](#operator_eq)|Перегружен. Назначает содержимое другой `concurrent_unordered_map` этого объекта. Этот метод не является безопасным в режиме параллелизма.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о `concurrent_unordered_map` см. в описании [параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concurrent_unordered_map.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="at"></a> в 

 Находит элемент в `concurrent_unordered_map` с заданным значением ключа... Данный метод безопасен в режиме параллелизма.  
  
```
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Параметры  
 `KVal`  
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
 Итератор на первый элемент в параллельном контейнере.  
  
##  <a name="cbegin"></a> cbegin 

 Возвращает константный итератор, указывающий на первый элемент в параллельном контейнере. Данный метод безопасен в режиме параллелизма.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Константный итератор на первый элемент в параллельном контейнере.  
  
##  <a name="cend"></a> cend 

 Возвращает константный итератор, указывающий на местоположение, следующему за последним элементом в параллельном контейнере. Данный метод безопасен в режиме параллелизма.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор const для к месту, следующему за последним элементом в параллельном контейнере.  
  
##  <a name="clear"></a> Снимите флажок 

 Удаляет все элементы в параллельном контейнере. Эта функция не безопасен в режиме параллелизма.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_unordered_map 

 Создает параллельный неупорядоченном сопоставлении.  
  
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
 `_Iterator`  
 Тип итератора ввода.  
  
 `_Number_of_buckets`  
 Начальное количество сегментов для этого в неупорядоченном сопоставлении.  
  
 `_Hasher`  
 Хэш-функции для этого в неупорядоченном сопоставлении.  
  
 `key_equality`  
 Функция сравнения на равенство для этого в неупорядоченном сопоставлении.  
  
 `_Allocator`  
 Распределитель для этого в неупорядоченном сопоставлении.  
  
 `_Begin`  
 Положение первого элемента в диапазоне копируемых элементов.  
  
 `_End`  
 Положение первого элемента после диапазона копируемых элементов.  
  
 `_Umap`  
 Исходный объект `concurrent_unordered_map` для копирования или перемещения элементов.  
  
### <a name="remarks"></a>Примечания  
 Все конструкторы хранят объект распределителя `_Allocator` и инициализировать неупорядоченном сопоставлении.  
  
 Первый конструктор определяет пустая карта начальной и явно указывает количество блоков, хэш-функции, функцию равенства и тип распределителя для использования.  
  
 Второй конструктор определяет распределитель для неупорядоченного карты.  
  
 Третий конструктор задает значения, предоставленные диапазоном итератора [ `_Begin`, `_End`).  
  
 Четвертый и пятый конструкторы определяют копию параллельных неупорядоченном сопоставлении `_Umap`.  
  
 Последний конструктор определяет перемещение параллельных неупорядоченном сопоставлении `_Umap`.  
  
##  <a name="count"></a> Счетчик 

 Подсчитывает количество элементов, соответствующих заданному ключу. Эта функция является безопасен в режиме параллелизма.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Параметры  
 `KVal`  
 Ключ, который нужно найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество времени, количество появлений ключа в контейнере.  
  
##  <a name="empty"></a> пустой 

 Проверяет отсутствие элементов. Данный метод безопасен в режиме параллелизма.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если параллельный контейнер пуст, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 При наличии параллельных вставок пуста ли параллельном контейнере может измениться сразу после вызова этой функции перед даже считать возвращаемое значение.  
  
##  <a name="end"></a> Конец 

 Возвращает итератор, указывающий к месту, следующему за последним элементом в параллельном контейнере. Данный метод безопасен в режиме параллелизма.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор к месту, следующему за последним элементом в параллельном контейнере.  
  
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
 `KVal`  
 Значение ключа для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [пары](http://msdn.microsoft.com/en-us/c5a37023-d939-4eb2-ae24-ce8e0cd4505d) где первый элемент является итератором до начала, а второй элемент — это итератор конец диапазона.  
  
### <a name="remarks"></a>Примечания  
 Это возможно для одновременных операций вставки вызвать дополнительные ключи, вставляемый после начала итератора и перед конечный итератор.  
  
##  <a name="find"></a> Найти 

 Определяет элемент, соответствующий указанному ключу. Эта функция является безопасен в режиме параллелизма.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Параметры  
 `KVal`  
 Значение ключа для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий расположение первый элемент, соответствующий ключ, указанный или итератора `end()` Если такого элемента не существует.  
  
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
  
##  <a name="insert"></a> Вставка 

 Добавляет элементы к `concurrent_unordered_map` объекта.  
  
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
 `_Iterator`  
 Тип итератора, используемый для вставки.  
  
 `V`  
 Тип значения, вставляемого в схеме.  
  
 `value`  
 Вставляемое значение.  
  
 `_Where`  
 Начальное расположение для поиска точки вставки.  
  
 `first`  
 Начало диапазона для вставки.  
  
 `last`  
 Конец диапазона для вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Пару, которая содержит итератор и логическое значение. Дополнительные сведения см.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член определяет, существует ли элемент X в последовательности, ключ которого имеет соответствующий порядок, `value`. Если нет, он создает такой элемент X и инициализирует его с `value`. Эта функция затем определяет итератор `where` , указывающий X. Если произошло вставкой, функция возвращает `std::pair(where, true)`. В противном случае возвращает значение `std::pair(where, false)`.  
  
 Вторая функция-член возвращает вставки ( `value`), с использованием `_Where` качестве отправной точки в управляемой последовательности для поиска курсор.  
  
 Третья функция-член вставляет последовательность значений элементов в диапазоне [ `first`, `last`).  
  
 Последние две функции-члены работают так же как первым двум, за исключением того, что `value` используется для создания вставленное значение.  
  
##  <a name="key_eq"></a> key_eq 

 Возвращает объект функции сравнения хранимых равенства.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект функции сравнения хранимых равенства.  
  
##  <a name="load_factor"></a> load_factor 

 Вычисляет и возвращает коэффициент загрузки текущего контейнера. Фактор нагрузки — количество элементов в контейнере, деленное на количество блоков.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Коэффициент загрузки для контейнера.  
  
##  <a name="max_load_factor"></a> max_load_factor 

 Возвращает или задает коэффициент максимальной нагрузки для контейнера. Коэффициент максимальной нагрузки является наибольшее количество элементов, чем может быть в одном контейнере оказывается перед контейнера роста своей внутренней таблицы.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Параметры  
 `_Newmax`  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая функция-член возвращает сохраненный коэффициент максимальной нагрузки. Вторая функция-член возвращает значение, но создает исключение [out_of_range](../../../standard-library/out-of-range-class.md) исключение, если недопустимый фактор нагрузки...  
  
##  <a name="max_size"></a> max_size 

 Возвращает максимальный размер параллельном контейнере, определить распределителем. Данный метод безопасен в режиме параллелизма.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное количество элементов, которые могут быть вставлены в этом параллельном контейнере.  
  
### <a name="remarks"></a>Примечания  
 Это значение верхней границы фактически может быть выше, чем то, что еще фактически может содержаться в контейнере.  
  
##  <a name="operator_at"></a> оператор] 

 Находит или вставляет элемент с указанным ключом. Данный метод безопасен в режиме параллелизма.  
  
```
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```  
  
### <a name="parameters"></a>Параметры  
 `KVal`  
 Значение ключа для  
  
 поиска или вставки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на значение данных найденного или вставленного элемента.  
  
### <a name="remarks"></a>Примечания  
 Если значение ключа аргумента не найдено, он вставляется вместе со значением по умолчанию для такого типа данных.  
  
 `operator[]` может использоваться для вставки элементов в сопоставление `m` с помощью `m[key] = DataValue;`, где `DataValue` — значение `mapped_type` элемента со значением ключа `key`.  
  
 При использовании `operator[]` для вставки элементов возвращаемая ссылка не отображает, меняет ли вставка уже существующий элемент или создает новый. Функции-члены `find` и [вставить](#insert) можно использовать для определения, является ли элемент с указанным ключом уже существует, перед вставкой.  
  
##  <a name="operator_eq"></a> оператор = 

 Назначает содержимое другой `concurrent_unordered_map` этого объекта. Этот метод не является безопасным в режиме параллелизма.  
  
```
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```  
  
### <a name="parameters"></a>Параметры  
 `_Umap`  
 Исходный объект `concurrent_unordered_map`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `concurrent_unordered_map` объекта.  
  
### <a name="remarks"></a>Примечания  
 После удаления всех существующих элементов в параллельном векторе `operator=` либо копирует, либо перемещает содержимое `_Umap` в параллельный вектор.  
  
##  <a name="rehash"></a> rehash 

 Повторно создает хэш-таблицу.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>Параметры  
 `_Buckets`  
 Требуемое число сегментов.  
  
### <a name="remarks"></a>Примечания  
 Функция-член устанавливает число сегментов не менее `_Buckets` и при необходимости перестраивает хэш-таблицу. Число контейнеров должно быть степенью числа 2. Если не является степенью 2, оно будет округлено до следующего наибольшего степени числа 2.  
  
 Он выдает [out_of_range](../../../standard-library/out-of-range-class.md) исключение, если число контейнеров, является недопустимым (0 или больше, чем максимальное количество блоков).  
  
##  <a name="size"></a> Размер 

 Возвращает число элементов в этом параллельном контейнере. Данный метод безопасен в режиме параллелизма.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число элементов в контейнере.  
  
### <a name="remarks"></a>Примечания  
 При наличии параллельных вставок число элементов в параллельном контейнере может измениться сразу после вызова этой функции даже до чтения возвращаемого значения.  
  
##  <a name="swap"></a> Поменять местами 

 Меняет местами содержимое двух `concurrent_unordered_map` объектов. Этот метод не является безопасным в режиме параллелизма.  
  
```
void swap(concurrent_unordered_map& _Umap);
```  
  
### <a name="parameters"></a>Параметры  
 `_Umap`  
 Объект `concurrent_unordered_map` для обмена.  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 Возвращает итератор на первый элемент в этом контейнере для конкретного сегмента.  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Bucket`  
 Индекс сегмента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий на начало сегмента.  
  
##  <a name="unsafe_bucket"></a> unsafe_bucket 

 Возвращает индекс сегмента, который сопоставляет указанный ключ в этом контейнере.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Параметры  
 `KVal`  
 Ключ элемента, поиск которого выполняется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс сегмента ключа в этом контейнере.  
  
##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count 

 Возвращает текущее число блоков в этом контейнере.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее количество сегментов в этом контейнере.  
  
##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size 

 Возвращает количество элементов из конкретного сегмента для этого контейнера.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Параметры  
 `_Bucket`  
 Контейнер для поиска.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущее количество сегментов в этом контейнере.  
  
##  <a name="unsafe_cbegin"></a> unsafe_cbegin 

 Возвращает итератор на первый элемент в этом контейнере для конкретного сегмента.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Bucket`  
 Индекс сегмента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий на начало сегмента.  
  
##  <a name="unsafe_cend"></a> unsafe_cend 

 Возвращает итератор к месту, следующему за последним элементом в конкретного сегмента.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Bucket`  
 Индекс сегмента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор, указывающий на начало сегмента.  
  
##  <a name="unsafe_end"></a> unsafe_end 

 Возвращает итератор последнего элемента в этом контейнере для конкретного сегмента.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Параметры  
 `_Bucket`  
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
 `_Where`  
 Положение итератора для удаления.  
  
 `_Begin`  
 Положение первого элемента в диапазоне элементов для удаления.  
  
 `_End`  
 Положение первого элемента за пределами диапазона элементов для удаления.  
  
 `KVal`  
 Значение ключа для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первые две функции-члена возвращают итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или `concurrent_unordered_map::end`(), если такой элемент не существует. Третья функция-член возвращает число элементов, которые она удаляет.  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член удаляет элемент управляемой последовательности, указанный параметром `_Where`. Вторая функция-член удаляет элементы в диапазоне [ `_Begin`, `_End`).  
  
 Третья функция-член удаляет элементы в диапазоне, ограниченном `concurrent_unordered_map::equal_range`(KVal).  
  
##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count 

 Возвращает максимальное количество блоков в этом контейнере.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Максимальное количество сегментов в этом контейнере.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Параллельные контейнеры и объекты](../../../parallel/concrt/parallel-containers-and-objects.md)



