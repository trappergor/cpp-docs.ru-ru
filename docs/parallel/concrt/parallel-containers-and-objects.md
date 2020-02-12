---
title: Параллельные контейнеры и объекты
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: 04b38fdc66a5c37a1780deaae4ae165f63238d93
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142902"
---
# <a name="parallel-containers-and-objects"></a>Параллельные контейнеры и объекты

Библиотека параллельных шаблонов (PPL) включает несколько контейнеров и объектов, которые обеспечивают потокобезопасный доступ к их элементам.

*Параллельный контейнер* обеспечивает потокобезопасный доступ к наиболее важным операциям. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. Функциональные возможности этих контейнеров похожи на C++ функции, предоставляемые стандартной библиотекой. Например, класс [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) похож на класс [std:: Vector](../../standard-library/vector-class.md) , за исключением того, что класс `concurrent_vector` позволяет добавлять элементы параллельно. Одновременно используйте параллельные контейнеры, для которых требуется доступ на чтение и запись к одному и тому же контейнеру.

*Параллельный объект* совместно используется компонентами. Процесс, который вычисляет состояние параллельного объекта в Parallel, дает тот же результат, что и другой процесс, который последовательно вычисляет одно и то же состояние. Класс [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) является одним из примеров параллельного типа объекта. Класс `combinable` позволяет выполнять вычисления параллельно, а затем объединять эти вычисления в окончательный результат. Используйте параллельные объекты, если в противном случае использовать механизм синхронизации, например мьютекс, для синхронизации доступа к общей переменной или ресурсу.

## <a name="top"></a> Разделы

В этом разделе подробно описаны следующие параллельные контейнеры и объекты.

Параллельные контейнеры:

- [Класс concurrent_vector](#vector)

   - [Различия между concurrent_vector и Vector](#vector-differences)

   - [Операции с параллелизмом](#vector-safety)

   - [Безопасность исключений](#vector-exceptions)

- [Класс concurrent_queue](#queue)

   - [Различия между concurrent_queue и очередью](#queue-differences)

   - [Операции с параллелизмом](#queue-safety)

   - [Поддержка итераторов](#queue-iterators)

- [Класс concurrent_unordered_map](#unordered_map)

   - [Различия между concurrent_unordered_map и unordered_map](#map-differences)

   - [Операции с параллелизмом](#map-safety)

- [Класс concurrent_unordered_multimap](#unordered_multimap)

- [Класс concurrent_unordered_set](#unordered_set)

- [Класс concurrent_unordered_multiset](#unordered_multiset)

Параллельные объекты:

- [Класс combinable](#combinable)

   - [Методы и функции](#combinable-features)

   - [Примеры](#combinable-examples)

## <a name="vector"></a>Класс concurrent_vector

Класс [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) является классом-контейнером последовательности, который, как и класс [std:: Vector](../../standard-library/vector-class.md) , обеспечивает случайный доступ к его элементам. Класс `concurrent_vector` позволяет выполнять операции добавочного и безопасного доступа к элементам. Операции добавления не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются надежными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода.

### <a name="vector-differences"></a>Различия между concurrent_vector и Vector

Класс `concurrent_vector` похож на класс `vector`. Сложность операций добавления, доступа к элементам и итераторов на объект `concurrent_vector` одинаковы для объекта `vector`. Следующие моменты иллюстрируют, где `concurrent_vector` отличается от `vector`.

- Операции добавления, доступа к элементам, итератора и обхода итератора для объекта `concurrent_vector` являются типобезопасными.

- Элементы можно добавлять только в конец объекта `concurrent_vector`. Класс `concurrent_vector` не предоставляет метод `insert`.

- Объект `concurrent_vector` не использует [семантику перемещения](../../cpp/rvalue-reference-declarator-amp-amp.md) при добавлении к ней.

- Класс `concurrent_vector` не предоставляет методы `erase` или `pop_back`. Как и в случае с `vector`, используйте метод [clear](reference/concurrent-vector-class.md#clear) , чтобы удалить все элементы из объекта `concurrent_vector`.

- Класс `concurrent_vector` не хранит свои элементы непрерывно в памяти. Таким образом, нельзя использовать класс `concurrent_vector` во всех способах использования массива. Например, для переменной с именем `v` типа `concurrent_vector`выражение `&v[0]+2` создает неопределенное поведение.

- Класс `concurrent_vector` определяет методы [grow_by](reference/concurrent-vector-class.md#grow_by) и [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) . Эти методы похожи на метод [изменения размера](reference/concurrent-vector-class.md#resize) , за исключением того, что они являются надежными в режиме параллелизма.

- Объект `concurrent_vector` не перемещает свои элементы при добавлении к нему или изменении его размера. Это позволяет существующим указателям и итераторам оставаться действительными во время параллельных операций.

- Среда выполнения не определяет специальную версию `concurrent_vector` для типа `bool`.

### <a name="vector-safety"></a>Операции с параллелизмом

Все методы, которые добавляют или увеличивают размер объекта `concurrent_vector` или обращаются к элементу в `concurrent_vector` объекте, являются типобезопасными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. Исключением из этого правила является метод `resize`.

В следующей таблице показаны общие методы `concurrent_vector` и операторы, которые являются типобезопасными в режиме параллелизма.

||||
|-|-|-|
|[at](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[begin](reference/concurrent-vector-class.md#begin)|[front](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[back](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[емкость](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[size](reference/concurrent-vector-class.md#size)|

Операции, предоставляемые средой выполнения для обеспечения C++ совместимости со стандартной библиотекой, например `reserve`, не являются надежными в режиме параллелизма. В следующей таблице показаны общие методы и операторы, которые не являются типобезопасными в режиме параллелизма.

|||
|-|-|
|[assign](reference/concurrent-vector-class.md#assign)|[reserve](reference/concurrent-vector-class.md#reserve)|
|[пусто](reference/concurrent-vector-class.md#clear)|[resize](reference/concurrent-vector-class.md#resize)|
|[оператор=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Операции, изменяющие значение существующих элементов, не являются надежными в режиме параллелизма. Используйте объект синхронизации, например объект [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) , чтобы синхронизировать параллельные операции чтения и записи с одним и тем же элементом данных. Дополнительные сведения об объектах синхронизации см. в разделе [структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md).

При преобразовании существующего кода, использующего `vector` для использования `concurrent_vector`, параллельные операции могут привести к изменению поведения приложения. Например, рассмотрим следующую программу, которая одновременно выполняет две задачи для объекта `concurrent_vector`. Первая задача добавляет дополнительные элементы в объект `concurrent_vector`. Вторая задача вычисляет сумму всех элементов в одном объекте.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Хотя метод `end` является типобезопасным, параллельный вызов метода [push_back](reference/concurrent-vector-class.md#push_back) вызывает изменение значения, возвращаемого `end`. Число элементов, которые проходит итератор, является неопределенным. Таким образом, эта программа может создавать различные результаты при каждом запуске. Если тип элемента нетривиальный, то может существовать состояние гонки между `push_back` и `end` вызовами. Метод `end` может возвращать элемент, который выделен, но не полностью инициализирован.

### <a name="vector-exceptions"></a>Безопасность исключений

Если операция увеличения или назначения создает исключение, состояние объекта `concurrent_vector` станет недопустимым. Поведение объекта `concurrent_vector`, который находится в недопустимом состоянии, не определено, если не указано иное. Однако деструктор всегда освобождает память, выделенную объектом, даже если объект находится в недопустимом состоянии.

Тип данных элементов Vector, `T`, должен соответствовать следующим требованиям. В противном случае поведение класса `concurrent_vector` не определено.

- Деструктор не должен вызывать исключение.

- Если конструктор по умолчанию или экземпляр создает исключение, деструктор не должен быть объявлен с помощью ключевого слова `virtual` и должен правильно работать с памятью, инициализированной нулем.

[[В начало](#top)]

## <a name="queue"></a>Класс concurrent_queue

Класс [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) , как и класс [std:: Queue](../../standard-library/queue-class.md) , позволяет получить доступ к элементам Front и back. Класс `concurrent_queue` позволяет выполнять операции постановки в очередь с параллелизмом и из очереди. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. Класс `concurrent_queue` также обеспечивает поддержку итератора, которая не является типобезопасным.

### <a name="queue-differences"></a>Различия между concurrent_queue и очередью

Класс `concurrent_queue` похож на класс `queue`. Следующие моменты иллюстрируют, где `concurrent_queue` отличается от `queue`.

- Операции постановки в очередь и вывода из очереди для объекта `concurrent_queue` являются надежными в режиме параллелизма.

- Класс `concurrent_queue` предоставляет поддержку итератора, которая не является надежной в режиме параллелизма.

- Класс `concurrent_queue` не предоставляет методы `front` или `pop`. Класс `concurrent_queue` заменяет эти методы, определяя метод [try_pop](reference/concurrent-queue-class.md#try_pop) .

- Класс `concurrent_queue` не предоставляет метод `back`. Таким образом, нельзя ссылаться на конец очереди.

- Класс `concurrent_queue` предоставляет метод [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) , а не метод `size`. Метод `unsafe_size` не является типобезопасным в режиме параллелизма.

### <a name="queue-safety"></a>Операции с параллелизмом

Все методы, которые помещаются в очередь или удаляются из `concurrent_queue` объекта, являются надежными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода.

В следующей таблице показаны общие методы `concurrent_queue` и операторы, которые являются типобезопасными в режиме параллелизма.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

Хотя метод `empty` является типобезопасным, параллельная операция может привести к увеличению или уменьшению очереди перед возвратом метода `empty`.

В следующей таблице показаны общие методы и операторы, которые не являются типобезопасными в режиме параллелизма.

|||
|-|-|
|[пусто](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

### <a name="queue-iterators"></a>Поддержка итераторов

`concurrent_queue` предоставляет итераторы, которые не являются надежными в режиме параллелизма. Рекомендуется использовать эти итераторы только для отладки.

Итератор `concurrent_queue` проходит по элементам только в прямом направлении. В следующей таблице показаны операторы, которые поддерживаются каждым итератором.

|Оператор|Description|
|--------------|-----------------|
|`operator++`|Переходит к следующему элементу в очереди. Этот оператор перегружен, чтобы обеспечить семантику до и после инкремента.|
|`operator*`|Извлекает ссылку на текущий элемент.|
|`operator->`|Извлекает указатель на текущий элемент.|

[[В начало](#top)]

## <a name="unordered_map"></a>Класс concurrent_unordered_map

Класс [Concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) является ассоциативным классом контейнера, который, как и класс [std:: unordered_map](../../standard-library/unordered-map-class.md) , управляет последовательностью различной длины элементов типа [std::p Air\<const Key, Ty >](../../standard-library/pair-structure.md). Неупорядоченную карту можно рассматривать как словарь, который позволяет добавить пару "ключ-значение" в или найти значение по ключу. Этот класс полезен при наличии нескольких потоков или задач, которые должны одновременно получить доступ к общему контейнеру, вставить в него или обновить его.

В следующем примере показана базовая структура для использования `concurrent_unordered_map`. В этом примере вставляются ключи символов в диапазоне ["a", "i"]. Так как порядок операций не определен, конечное значение для каждого ключа также не определено. Однако можно выполнять операции вставки параллельно.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Пример, использующий `concurrent_unordered_map` для параллельного выполнения операции Map и reduce, см. в разделе [как выполнять операции Map и reduce параллельно](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

### <a name="map-differences"></a>Различия между concurrent_unordered_map и unordered_map

Класс `concurrent_unordered_map` похож на класс `unordered_map`. Следующие моменты иллюстрируют, где `concurrent_unordered_map` отличается от `unordered_map`.

- Методы `erase`, `bucket`, `bucket_count`и `bucket_size` называются `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`и `unsafe_bucket_size`соответственно. Соглашение об именовании `unsafe_` указывает, что эти методы не являются надежными в режиме параллелизма. Дополнительные сведения о безопасности параллелизма см. в разделе [операции с параллелизмом](#map-safety).

- Операции INSERT не делают недействительными существующие указатели или итераторы и не изменяют порядок элементов, которые уже существуют на карте. Операции вставки и обхода могут выполняться параллельно.

- `concurrent_unordered_map` поддерживает только прямую итерацию.

- Вставка не делает недействительными или не обновляет итераторы, возвращаемые `equal_range`. Вставка может добавлять неравные элементы в конец диапазона. Итератор begin указывает на равный элемент.

Чтобы избежать взаимоблокировки, метод `concurrent_unordered_map` удерживает блокировку при вызове распределителя памяти, хэш-функций или другого пользовательского кода. Кроме того, необходимо убедиться, что хэш-функция всегда вычисляет равные ключи одинаковым значением. Лучшие хэш-функции распределяют ключи равномерно через пространство хэш-кода.

### <a name="map-safety"></a>Операции с параллелизмом

Класс `concurrent_unordered_map` позволяет выполнять типобезопасные операции вставки и доступа к элементам. Операции вставки не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются надежными в режиме параллелизма. В данном случае, безопасность с параллелизмом означает, что указатели или итераторы всегда действительны. Не гарантируется инициализация элементов или определенный порядок обхода. В следующей таблице показаны часто используемые методы `concurrent_unordered_map` и операторы, которые являются типобезопасными в режиме параллелизма.

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|

Несмотря на то, что метод `count` можно безопасно вызывать из параллельно выполняющихся потоков, различные потоки могут получать разные результаты, если новое значение одновременно вставляется в контейнер.

В следующей таблице показаны часто используемые методы и операторы, которые не являются типобезопасными.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[оператор=](reference/concurrent-unordered-map-class.md#operator_eq)

В дополнение к этим методам любой метод, начинающийся с `unsafe_`, также не является типобезопасным в режиме параллелизма.

[[В начало](#top)]

## <a name="unordered_multimap"></a>Класс concurrent_unordered_multimap

Класс [Concurrency:: concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) похож на класс `concurrent_unordered_map`, за исключением того, что он позволяет сопоставлять несколько значений с одним и тем же ключом. Он также отличается от `concurrent_unordered_map` следующими способами.

- Метод [concurrent_unordered_multimap:: INSERT](reference/concurrent-unordered-multimap-class.md#insert) возвращает итератор вместо `std::pair<iterator, bool>`.

- Класс `concurrent_unordered_multimap` не предоставляет `operator[]` и метод `at`.

В следующем примере показана базовая структура для использования `concurrent_unordered_multimap`. В этом примере вставляются ключи символов в диапазоне ["a", "i"]. `concurrent_unordered_multimap` позволяет ключу иметь несколько значений.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[В начало](#top)]

## <a name="unordered_set"></a>Класс concurrent_unordered_set

Класс [Concurrency:: concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) похож на класс `concurrent_unordered_map`, за исключением того, что он управляет значениями вместо пар "ключ — значение". Класс `concurrent_unordered_set` не предоставляет `operator[]` и метод `at`.

В следующем примере показана базовая структура для использования `concurrent_unordered_set`. В этом примере вставляются символьные значения в диапазоне ["a", "i"]. Операции вставки можно выполнять параллельно.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[В начало](#top)]

## <a name="unordered_multiset"></a>Класс concurrent_unordered_multiset

Класс [Concurrency:: concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) похож на класс `concurrent_unordered_set`, за исключением того, что он допускает дублирование значений. Он также отличается от `concurrent_unordered_set` следующими способами.

- Метод [concurrent_unordered_multiset:: INSERT](reference/concurrent-unordered-multiset-class.md#insert) возвращает итератор вместо `std::pair<iterator, bool>`.

- Класс `concurrent_unordered_multiset` не предоставляет `operator[]` и метод `at`.

В следующем примере показана базовая структура для использования `concurrent_unordered_multiset`. В этом примере вставляются символьные значения в диапазоне ["a", "i"]. `concurrent_unordered_multiset` позволяет несколько раз встречаться значение.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[В начало](#top)]

## <a name="combinable"></a>Класс combinable

Класс [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) обеспечивает многократно используемое локальное хранилище потока, которое позволяет выполнять детализированные вычисления, а затем объединять эти вычисления в окончательный результат. Объект `combinable` можно рассматривать как переменную уменьшения.

Класс `combinable` полезен при наличии ресурса, совместно используемого несколькими потоками или задачами. Класс `combinable` помогает исключить общее состояние, предоставляя доступ к общим ресурсам без блокировки. Таким образом, этот класс предоставляет альтернативу использованию механизма синхронизации, например мьютекса, для синхронизации доступа к общим данным из нескольких потоков.

### <a name="combinable-features"></a>Методы и функции

В следующей таблице показаны некоторые важные методы класса `combinable`. Дополнительные сведения о всех методах класса `combinable` см. в разделе [класс combinable](../../parallel/concrt/reference/combinable-class.md).

|Метод|Description|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|Извлекает ссылку на локальную переменную, связанную с текущим контекстом потока.|
|[пусто](reference/combinable-class.md#clear)|Удаляет все локальные переменные потока из объекта `combinable`.|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Использует предоставленную функцию combine для создания окончательного значения из набора всех локальных вычислений потока.|

Класс `combinable` — это класс шаблона, параметризованный в окончательном объединенном результате. При вызове конструктора по умолчанию тип параметра шаблона `T` должен иметь конструктор по умолчанию и конструктор копии. Если тип параметра шаблона `T` не имеет конструктора по умолчанию, вызовите перегруженную версию конструктора, которая принимает в качестве параметра функцию инициализации.

Дополнительные данные можно хранить в `combinable` объекте после вызова методов [Combine](reference/combinable-class.md#combine) или [combine_each](reference/combinable-class.md#combine_each) . Методы `combine` и `combine_each` также можно вызывать несколько раз. Если локальное значение в объекте `combinable` не меняется, методы `combine` и `combine_each` возвращают один и тот же результат при каждом вызове.

### <a name="combinable-examples"></a> Примеры

Примеры использования класса `combinable` см. в следующих разделах:

- [Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[В начало](#top)]

## <a name="related-topics"></a>См. также

[Практическое руководство. Использование параллельных контейнеров для повышения эффективности](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Показывает, как использовать параллельные контейнеры для эффективного хранения и доступа к данным в параллельном режиме.

[Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Показывает, как использовать класс `combinable` для исключения общего состояния и, таким образом, повысить производительность.

[Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Показывает, как использовать функцию `combine` для слияния локальных наборов данных потока.

[Библиотека параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Описывает библиотеку PPL, которая предоставляет императивную модель программирования, которая способствует масштабируемости и простоте использования при разработке параллельных приложений.

## <a name="reference"></a>Справочник

[Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)

[Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)

[Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[Класс concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[Класс concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[Класс concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[Класс combinable](../../parallel/concrt/reference/combinable-class.md)
