---
title: Параллельные контейнеры и объекты
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: f3fb2bb57c8bcf65de0a7f74f2992050d8257429
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363046"
---
# <a name="parallel-containers-and-objects"></a>Параллельные контейнеры и объекты

Библиотека параллельных шаблонов (PPL) включает в себя несколько контейнеров и объектов, обеспечивающих безопасный доступ к их элементам.

*Параллельный контейнер* обеспечивает параллельно-безопасный доступ к наиболее важным операциям. Здесь, параллель-безопасные указатели средств или итераторы всегда действительны. Это не гарантия инициализации элементов или конкретного порядка обхода. Функциональность этих контейнеров напоминает те, которые предоставляются Стандартной библиотекой СЗ. Например, [параллелизм::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класс напоминает [std::vector](../../standard-library/vector-class.md) class, за исключением того, что `concurrent_vector` класс позволяет придатить элементы параллельно. Используйте одновременные контейнеры, когда у вас есть параллельный код, который требует как чтения, так и записи доступа к тому же контейнеру.

*Параллельный объект* распределяется одновременно между компонентами. Процесс, который вычисляет состояние параллельного объекта, дает тот же результат, что и другой процесс, который вычисляет то же состояние последовательно. [Параллель::комбинированный](../../parallel/concrt/reference/combinable-class.md) класс является одним из примеров параллельного типа объекта. Класс `combinable` позволяет выполнять вычисления параллельно, а затем объединить эти вычисления в конечный результат. Для синхронизации доступа к общей переменной или ресурсу используйте одновременные объекты, если в противном случае вы используете механизм синхронизации, например, mutex.

## <a name="sections"></a><a name="top"></a>Разделы

Эта тема подробно описывает следующие параллельные контейнеры и объекты.

Параллельные контейнеры:

- [Класс concurrent_vector](#vector)

  - [Различия между concurrent_vector и вектором](#vector-differences)

  - [Параллель-Безопасные операции](#vector-safety)

  - [Безопасность исключений](#vector-exceptions)

- [Класс concurrent_queue](#queue)

  - [Различия между concurrent_queue и очередью](#queue-differences)

  - [Параллель-Безопасные операции](#queue-safety)

  - [Поддержка итератора](#queue-iterators)

- [класс concurrent_unordered_map](#unordered_map)

  - [Различия между concurrent_unordered_map и unordered_map](#map-differences)

  - [Параллель-Безопасные операции](#map-safety)

- [Класс concurrent_unordered_multimap](#unordered_multimap)

- [Класс concurrent_unordered_set](#unordered_set)

- [Класс concurrent_unordered_multiset](#unordered_multiset)

Параллельные объекты:

- [Класс combinable](#combinable)

  - [Методы и особенности](#combinable-features)

  - [Примеры](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a>класс concurrent_vector

[Параллел::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класс представляет собой класс контейнеров последовательности, который, как и [класс std:Vector,](../../standard-library/vector-class.md) позволяет случайным образом получить доступ к его элементам. Класс `concurrent_vector` позволяет операциям по безопасному параллелизму и элементам доступа. Операции приложения не аннулируют существующие указатели или итераторы. Доступ и операции по прохождению также являются валютными. Здесь, параллель-безопасные указатели средств или итераторы всегда действительны. Это не гарантия инициализации элементов или конкретного порядка обхода.

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a>Различия между concurrent_vector и вектором

Класс `concurrent_vector` очень напоминает `vector` класс. Сложность операций доступа к приложению, `concurrent_vector` `vector` элемента и итератора на объекте такая же, как и для объекта. Следующие моменты `concurrent_vector` иллюстрируют, где отличается от: `vector`

- Приложение, доступ к элементам, доступ итератора и операции `concurrent_vector` обхода итератора на объекте являются валютными.

- Элементы можно добавлять только `concurrent_vector` к концу объекта. Класс `concurrent_vector` не предоставляет `insert` метод.

- Объект `concurrent_vector` не использует [семантику перемещения](../../cpp/rvalue-reference-declarator-amp-amp.md) при приложении к нему.

- Класс `concurrent_vector` не предоставляет `erase` или `pop_back` методы. Как `vector`и в том, что используйте `concurrent_vector` [четкий](reference/concurrent-vector-class.md#clear) метод для удаления всех элементов с объекта.

- Класс `concurrent_vector` не хранит свои элементы в памяти. Таким образом, вы `concurrent_vector` не можете использовать класс всеми способами, которые можно использовать массив. Например, для переменной, `concurrent_vector`названной `&v[0]+2` `v` типом, выражение производит неопределенное поведение.

- Класс `concurrent_vector` определяет [методы grow_by](reference/concurrent-vector-class.md#grow_by) и [grow_to_at_least.](reference/concurrent-vector-class.md#grow_to_at_least) Эти методы напоминают метод [повторного размера,](reference/concurrent-vector-class.md#resize) за исключением того, что они являются валютными., безопасными.

- Объект `concurrent_vector` не перемещает свои элементы при придатке к нему или изменяет его размер. Это позволяет существующим указателям и итераторам оставаться действительными во время параллельных операций.

- Время выполнения не определяет специализированную `concurrent_vector` версию для типа. `bool`

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a>Параллель-Безопасные операции

Все методы, которые придативают `concurrent_vector` или увеличивают размер объекта `concurrent_vector` или получают доступ к элементу объекта, являются валютными. Здесь, параллель-безопасные указатели средств или итераторы всегда действительны. Это не гарантия инициализации элементов или конкретного порядка обхода. Исключением из этого `resize` правила является метод.

В следующей таблице `concurrent_vector` показаны общие методы и операторы, которые являются валютными., безопасными.

||||
|-|-|-|
|[В](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[оператор&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[Начать](reference/concurrent-vector-class.md#begin)|[Перед](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[Назад](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[Емкость](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[Пустой](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[Размер](reference/concurrent-vector-class.md#size)|

Операции, которые время выполнения обеспечивает совместимость со Стандартной библиотекой `reserve`СЗ, например, не являются валютными. В следующей таблице показаны общие методы и операторы, которые не являются валютными.

|||
|-|-|
|[Назначить](reference/concurrent-vector-class.md#assign)|[Заповедник](reference/concurrent-vector-class.md#reserve)|
|[Ясно](reference/concurrent-vector-class.md#clear)|[Изменения размера](reference/concurrent-vector-class.md#resize)|
|[оператора](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Операции, изменяющие значение существующих элементов, не являются валютными. Используйте объект синхронизации, такой как [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) объект для синхронизации одновременного чтения и записи операций на один и тот же элемент данных. Для получения дополнительной информации об [Synchronization Data Structures](../../parallel/concrt/synchronization-data-structures.md)объектах синхронизации см.

При преобразовании существующего кода, который используется `vector` для использования, `concurrent_vector`параллельные операции могут привести к изменению поведения приложения. Например, рассмотрим следующую программу, которая `concurrent_vector` одновременно выполняет две задачи на объекте. Первая задача придатит `concurrent_vector` дополнительные элементы к объекту. Вторая задача вычисляет сумму всех элементов одного объекта.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Хотя `end` метод является параллельно-безопасным, параллельный вызов [push_back](reference/concurrent-vector-class.md#push_back) методом `end` приводит к изменению значения, которое возвращается. Количество элементов, проходящих итератор, неопределенным. Таким образом, эта программа может производить другой результат каждый раз, когда вы запустите его. Когда тип элемента нетривиален, может существовать условие `push_back` `end` гонки между вызовами и вызовами. Метод `end` может вернуть выделенный элемент, но не полностью инициализированный.

### <a name="exception-safety"></a><a name="vector-exceptions"></a>Безопасность исключений

Если операция роста или назначения выбрасывает исключение, `concurrent_vector` состояние объекта становится недействительным. Поведение `concurrent_vector` объекта, наемного состояния, не определено, если не указано иное. Однако деструктор всегда освобождает память, которую выделяет объект, даже если объект находится в недействительном состоянии.

Тип данных векторных `T`элементов, должен соответствовать следующим требованиям. В противном случае `concurrent_vector` поведение класса не определено.

- Деструктор не должен бросать.

- Если конструктор по умолчанию или копии бросает, деструктор `virtual` не должен быть объявлен с помощью ключевого слова, и он должен работать правильно с нулевым инициализированной памяти.

[Сверху](#top)

## <a name="concurrent_queue-class"></a><a name="queue"></a>класс concurrent_queue

[Параллель::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) класс, как [и класс std::queue](../../standard-library/queue-class.md) класса, позволяет получить доступ к его передние и задние элементы. Класс `concurrent_queue` позволяет проводить операции по безопасному конкеи и декейке. Здесь, параллель-безопасные указатели средств или итераторы всегда действительны. Это не гарантия инициализации элементов или конкретного порядка обхода. Класс `concurrent_queue` также предоставляет поддержку итератора, которая не является безопасной для параллелизма.

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a>Различия между concurrent_queue и очередью

Класс `concurrent_queue` очень напоминает `queue` класс. Следующие моменты `concurrent_queue` иллюстрируют, где отличается от: `queue`

- Операции enqueue и dequeue на объекте `concurrent_queue` являются валютными.

- Класс `concurrent_queue` предоставляет поддержку итератора, которая не является безопасной для параллелизма.

- Класс `concurrent_queue` не предоставляет `front` или `pop` методы. Класс `concurrent_queue` заменяет эти методы, определяя [try_pop](reference/concurrent-queue-class.md#try_pop) метод.

- Класс `concurrent_queue` не предоставляет `back` метод. Таким образом, нельзя ссылаться на конец очереди.

- Класс `concurrent_queue` предоставляет [метод unsafe_size](reference/concurrent-queue-class.md#unsafe_size) вместо `size` метода. Метод `unsafe_size` не является валютным.

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a>Параллель-Безопасные операции

Все методы, которые выстраиваются `concurrent_queue` в объект или отклоняются от них, являются безопасными для валют. Здесь, параллель-безопасные указатели средств или итераторы всегда действительны. Это не гарантия инициализации элементов или конкретного порядка обхода.

В следующей таблице `concurrent_queue` показаны общие методы и операторы, которые являются валютными., безопасными.

|||
|-|-|
|[Пустой](reference/concurrent-queue-class.md#empty)|[Нажмите](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

Хотя `empty` метод является параллельно-безопасным, одновременные операции могут привести `empty` к росту или сжатию очереди до возвращения метода.

В следующей таблице показаны общие методы и операторы, которые не являются валютными.

|||
|-|-|
|[Ясно](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

### <a name="iterator-support"></a><a name="queue-iterators"></a>Поддержка итератора

Предоставляет `concurrent_queue` итераторы, которые не являются валютными безопасными. Мы рекомендуем использовать эти итераторы только для отладки.

Итератор `concurrent_queue` пересекает элементы только в переднем направлении. В следующей таблице показаны операторы, которых поддерживает каждый итератор.

|Оператор|Описание|
|--------------|-----------------|
|`operator++`|Авансы к следующему элементу в очереди. Этот оператор перегружен, чтобы обеспечить как предварительное увеличение, так и пост-приращение семантики.|
|`operator*`|Извлекает ссылку на текущий элемент.|
|`operator->`|Извлекает указатель на текущий элемент.|

[Сверху](#top)

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a>класс concurrent_unordered_map

[Параллель::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) класс ассоциативного класса контейнера, который, так же, как [std::unordered_map](../../standard-library/unordered-map-class.md) класса, контролирует различную последовательность элементов типа [std::pair\<const Key, Ty>](../../standard-library/pair-structure.md). Думайте о неупорядоченной карте как о словаре, который можно добавить пару ключей и значений или посмотреть значение по ключу. Этот класс полезен, когда у вас есть несколько потоков или задач, которые должны одновременно получить доступ к общему контейнеру, вставить в него или обновить его.

Ниже приводится базовая структура `concurrent_unordered_map`для использования . Этот пример вставляет клавиши символов в диапазоне 'a', 'i'. Поскольку порядок операций не определен, конечная стоимость для каждого ключа также не определена. Тем не менее, это безопасно для выполнения вставки параллельно.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Например, для `concurrent_unordered_map` выполнения карты и параллельного сокращения операций см., [как: Выполнить карту и сократить операции параллельно.](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a>Различия между concurrent_unordered_map и unordered_map

Класс `concurrent_unordered_map` очень напоминает `unordered_map` класс. Следующие моменты `concurrent_unordered_map` иллюстрируют, где отличается от: `unordered_map`

- `erase`Названы `bucket` `bucket_count`и `bucket_size` методы `unsafe_erase`, `unsafe_bucket` `unsafe_bucket_count`и `unsafe_bucket_size`соответственно. Конвенция `unsafe_` о наименовании указывает на то, что эти методы не являются валютными. Для получения дополнительной информации о безопасности параллелизма, [см.](#map-safety)

- Операции вставки не аннулируют существующие указатели или итераторы и не меняют порядок элементов, которые уже существуют на карте. Операции вставки и прохождения могут происходить одновременно.

- `concurrent_unordered_map`поддерживает только передний итерации.

- Вставка не аннулирует и не обновляет итераторы, которые `equal_range`возвращаются. Вставка может придатить неравные элементы к концу диапазона. Начинаюй итератор указывает на равный элемент.

Чтобы избежать взаимоблокировки, `concurrent_unordered_map` ни один метод удержания блокировки при вызове салликататора памяти, функций хэша или другого пользовательского кода. Кроме того, необходимо убедиться, что функция хэша всегда оценивает равные клавиши с тем же значением. Лучшие хэш-функции равномерно распределяют клавиши по пространству хэш-кода.

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a>Параллель-Безопасные операции

Класс `concurrent_unordered_map` позволяет осуществлять операции по вставке и доступу к элементам. Операции вставки не аннулируют существующие указатели или итераторы. Доступ и операции по прохождению также являются валютными. Здесь, параллель-безопасные указатели средств или итераторы всегда действительны. Это не гарантия инициализации элементов или конкретного порядка обхода. В следующей таблице `concurrent_unordered_map` показаны широко используемые методы и операторы, которые являются валютными.

|||||
|-|-|-|-|
|[В](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[Key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[оператор&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[Вставить](reference/concurrent-unordered-map-class.md#insert)|`size`|

Хотя `count` метод можно безопасно вызывать из одновременно работающих потоков, различные потоки могут получать различные результаты, если новое значение одновременно вставляется в контейнер.

В следующей таблице показаны широко используемые методы и операторы, которые не являются безопасными для параллелизма.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[оператора](reference/concurrent-unordered-map-class.md#operator_eq)

В дополнение к этим методам, любой метод, который начинается с `unsafe_` также не является параллель-безопасным.

[Сверху](#top)

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a>класс concurrent_unordered_multimap

[Параллель::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) класс очень напоминает `concurrent_unordered_map` класс, за исключением того, что он позволяет нескольким значениям отображение одного и того же ключа. Он также отличается от `concurrent_unordered_map` следующих способов:

- В [concurrent_unordered_multimap::вставка](reference/concurrent-unordered-multimap-class.md#insert) метод возвращает итератор вместо `std::pair<iterator, bool>`.

- Класс `concurrent_unordered_multimap` не предоставляет `operator[]` ни `at` метода.

Ниже приводится базовая структура `concurrent_unordered_multimap`для использования . Этот пример вставляет клавиши символов в диапазоне 'a', 'i'. `concurrent_unordered_multimap`позволяет ключу иметь несколько значений.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[Сверху](#top)

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a>класс concurrent_unordered_set

[Параллель::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) класс очень напоминает `concurrent_unordered_map` класс, за исключением того, что он управляет значениями вместо ключевых и значений пар. Класс `concurrent_unordered_set` не предоставляет `operator[]` ни `at` метода.

Ниже приводится базовая структура `concurrent_unordered_set`для использования . Этот пример вставляет значения символов в диапазон «a», «i». Это безопасно для выполнения вставок параллельно.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[Сверху](#top)

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a>concurrent_unordered_multiset класс

[Параллель::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) класс очень напоминает `concurrent_unordered_set` класс, за исключением того, что он позволяет дублировать значения. Он также отличается от `concurrent_unordered_set` следующих способов:

- В [concurrent_unordered_multiset::вставка](reference/concurrent-unordered-multiset-class.md#insert) метод возвращает итератор вместо `std::pair<iterator, bool>`.

- Класс `concurrent_unordered_multiset` не предоставляет `operator[]` ни `at` метода.

Ниже приводится базовая структура `concurrent_unordered_multiset`для использования . Этот пример вставляет значения символов в диапазон «a», «i». `concurrent_unordered_multiset`позволяет значение происходить несколько раз.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[Сверху](#top)

## <a name="combinable-class"></a><a name="combinable"></a>комбинированный класс

[Параллель::комбинированный](../../parallel/concrt/reference/combinable-class.md) класс обеспечивает многоразовое хранилище потоков-локальных, что позволяет выполнять мелкозернистые вычисления, а затем сливать эти вычисления в конечный результат. Объект `combinable` можно рассматривать как переменную уменьшения.

Класс `combinable` полезен, когда у вас есть ресурс, который разделяется между несколькими потоками или задачами. Класс `combinable` помогает устранить совместное состояние, предоставляя доступ к общим ресурсам без блокировки. Таким образом, этот класс предоставляет альтернативу использованию механизма синхронизации, например, mutex, для синхронизации доступа к общим данным из нескольких потоков.

### <a name="methods-and-features"></a><a name="combinable-features"></a>Методы и особенности

В следующей таблице показаны некоторые `combinable` важные методы класса. Для получения дополнительной `combinable` информации обо всех методах класса [см.](../../parallel/concrt/reference/combinable-class.md)

|Метод|Описание|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|Извлекает ссылку на локальную переменную, связанную с текущим контекстом потока.|
|[Ясно](reference/combinable-class.md#clear)|Удаляет все локальные переменные `combinable` потока из объекта.|
|[Объединить](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Использует предоставленную функцию комбайна для создания конечного значения из набора всех локальных вычислений.|

Класс `combinable` представляет собой класс шаблонов, который параметрызируется в конечном объединенном результате. Если вы называете конструктор `T` по умолчанию, тип параметра шаблона должен иметь конструктор по умолчанию и конструктор копии. Если `T` тип параметра шаблона не имеет конструктора по умолчанию, позвоните в перегруженную версию конструктора, которая использует функцию инициализации в качестве параметра.

Вы можете хранить дополнительные данные в объекте `combinable` после вызова [комбайна](reference/combinable-class.md#combine) или [combine_each](reference/combinable-class.md#combine_each) методов. Вы также можете `combine` `combine_each` вызвать и методы несколько раз. Если локальное значение `combinable` в объекте не изменяется, `combine` методы и `combine_each` методы производят один и тот же результат каждый раз, когда они вызываются.

### <a name="examples"></a><a name="combinable-examples"></a>Примеры

Для примеров использования `combinable` класса см.

- [Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[Сверху](#top)

## <a name="related-topics"></a>См. также

[Практическое руководство. Использование параллельных контейнеров для повышения эффективности](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
Показывает, как использовать параллельные контейнеры для эффективного хранения и доступа к данным параллельно.

[Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Показывает, как `combinable` использовать класс для устранения общего состояния и тем самым повышает производительность.

[Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Показывает, как `combine` использовать функцию для слияния локальных наборов данных.

[Библиотека параллельных шаблонов](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Описывает PPL, которая обеспечивает императивную модель программирования, которая способствует масштабируемости и простоте использования для разработки одновременных приложений.

## <a name="reference"></a>Справочник

[Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)

[Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)

[класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[Класс concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[Класс concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[Класс concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[Класс combinable](../../parallel/concrt/reference/combinable-class.md)
