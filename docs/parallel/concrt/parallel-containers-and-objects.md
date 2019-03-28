---
title: Параллельные контейнеры и объекты
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: bcf3ead9fe945ecb2246fdb28b7f67cd51b1238b
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565952"
---
# <a name="parallel-containers-and-objects"></a>Параллельные контейнеры и объекты

Библиотека параллельных шаблонов (PPL) содержит несколько контейнеров и объектов, предоставляющих потокобезопасный доступ к своим элементам.

Объект *параллельном контейнере* предоставляет безопасный в отношении параллелизма доступ к наиболее важные операции. Функциональные возможности этих контейнеров похож на те, которые предоставляются механизмами стандартной библиотеки C++. Например [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класс похож на [std::vector](../../standard-library/vector-class.md) класса, за исключением случаев, `concurrent_vector` класс позволяет добавлять элементы в параллельном режиме. Используйте параллельные контейнеры, при наличии параллельный код, требующий чтение и запись в тот же контейнер.

Объект *параллельный объект* совместно используется между компонентами. Процесс, который вычисляет состояние параллельного объекта в параллельном режиме дает тот же результат, как другой процесс, который вычисляет то же состояние последовательно. [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс является одним из примеров типом параллельных объектов. `combinable` Класс позволяет выполнять вычисления в параллельном режиме, а затем объединять результаты этих вычислений в итоговый результат. Параллельные объекты следует используйте, когда в противном случае используется механизм синхронизации, к примеру, семафор для синхронизации доступа к общей переменной или ресурсу.

##  <a name="top"></a> Разделы

В этом разделе описываются следующие параллельные контейнеры и объекты подробно.

Параллельные контейнеры

- [Класс concurrent_vector](#vector)

   - [Различия между concurrent_vector и vector](#vector-differences)

   - [Параллельно безопасных операций](#vector-safety)

   - [Исключения безопасности](#vector-exceptions)

- [Класс concurrent_queue](#queue)

   - [Различия между concurrent_queue и очереди](#queue-differences)

   - [Параллельно безопасных операций](#queue-safety)

   - [Поддержка итераторов](#queue-iterators)

- [Класс concurrent_unordered_map](#unordered_map)

   - [Различия между concurrent_unordered_map и unordered_map](#map-differences)

   - [Параллельно безопасных операций](#map-safety)

- [Класс concurrent_unordered_multimap](#unordered_multimap)

- [Класс concurrent_unordered_set](#unordered_set)

- [Класс concurrent_unordered_multiset](#unordered_multiset)

Параллельные объекты

- [Класс combinable](#combinable)

   - [Методы и функции](#combinable-features)

   - [Примеры](#combinable-examples)

##  <a name="vector"></a> Класс concurrent_vector

[Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класс — это класс контейнера последовательности, так же, как [std::vector](../../standard-library/vector-class.md) класса, позволяет осуществлять доступ к его элементам. `concurrent_vector` Позволяет параллельно безопасно добавить и элемент доступа к операциям. Добавление операций не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются безопасными в режиме параллелизма.

###  <a name="vector-differences"></a> Различия между concurrent_vector и vector

`concurrent_vector` Класс сильно напоминает `vector` класса. Сложность операции доступа итератора, доступ к элементам и append `concurrent_vector` объекта одинаковы как для `vector` объекта. Далее показано, где `concurrent_vector` отличается от `vector`:

- Присоединения, доступ к элементам, итератора и выполнять операции обхода итератора на `concurrent_vector` объект являются безопасными в режиме параллелизма.

- Можно добавить элементы только до конца массива `concurrent_vector` объекта. `concurrent_vector` Класс не предоставляет `insert` метод.

- Объект `concurrent_vector` объект не использовал [семантику перемещения](../../cpp/rvalue-reference-declarator-amp-amp.md) при добавлении к нему.

- `concurrent_vector` Класс не предоставляет `erase` или `pop_back` методы. Как и в `vector`, использовать [снимите](reference/concurrent-vector-class.md#clear) метод, чтобы удалить все элементы из `concurrent_vector` объекта.

- `concurrent_vector` Не хранятся его элементы последовательно в памяти. Следовательно, нельзя использовать `concurrent_vector` класс во всех отношениях, что можно использовать массив. Например, для переменной с именем `v` типа `concurrent_vector`, выражение `&v[0]+2` выдает неопределенное поведение.

- `concurrent_vector` Класс определяет [grow_by](reference/concurrent-vector-class.md#grow_by) и [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) методы. Эти методы аналогичны [изменение размера](reference/concurrent-vector-class.md#resize) метода, за исключением того, что они являются безопасными в режиме параллелизма.

- Объект `concurrent_vector` объекта не перемещайте его элементы, добавьте к нему или изменить ее размер. Благодаря этому существующие указатели и итераторы остаются действительными при выполнении параллельных операций.

- Среда выполнения не определяет специальную версию `concurrent_vector` для типа `bool`.

###  <a name="vector-safety"></a> Параллельно безопасных операций

Все методы, добавляющие увеличить размер `concurrent_vector` объекта или доступа к элементу в `concurrent_vector` , являются безопасными в режиме параллелизма. Исключением из этого правила является `resize` метод.

В следующей таблице приведены распространенные `concurrent_vector` методы и операторы, которые являются безопасными в режиме параллелизма.

||||
|-|-|-|
|[at](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[begin](reference/concurrent-vector-class.md#begin)|[front](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[back](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[capacity](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[size](reference/concurrent-vector-class.md#size)|

Операции, которые среда выполнения предоставляет для обеспечения совместимости со стандартной библиотекой C++, например, `reserve`, не являются безопасными в режиме параллелизма. Ниже приведены наиболее распространенные методы и операторы, которые не являются безопасными в режиме параллелизма.

|||
|-|-|
|[assign](reference/concurrent-vector-class.md#assign)|[reserve](reference/concurrent-vector-class.md#reserve)|
|[clear](reference/concurrent-vector-class.md#clear)|[resize](reference/concurrent-vector-class.md#resize)|
|[оператор=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

Операции, которые изменяют значение существующих элементов не нарушающих параллельность. Использовать объект синхронизации, например [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) объект для синхронизации одновременных потоков чтения и записи один и тот же элемент данных. Дополнительные сведения об объектах синхронизации см. в разделе [структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md).

При преобразовании существующего кода, использующего `vector` использовать `concurrent_vector`, одновременных операций может привести к поведение приложения. Например, рассмотрим следующую программу, параллельно выполняет две задачи на `concurrent_vector` объекта. Первая задача добавляет дополнительные элементы для `concurrent_vector` объекта. Вторая задача вычисляет сумму всех элементов в том же объекте.

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

Несмотря на то что `end` метод безопасен в режиме параллелизма, параллельный вызов [push_back](reference/concurrent-vector-class.md#push_back) метод приводит значения, возвращенного `end` для изменения. Число элементов, которые проходит через итератор не определен. Таким образом эта программа может привести к другой результат при каждом его выполнении.

###  <a name="vector-exceptions"></a> Исключения безопасности

Если операции увеличения или назначения исключение, состояние `concurrent_vector` объект становится недействительным. Поведение `concurrent_vector` объект, который находится в недопустимом состоянии не определено, если не указано иное. Тем не менее деструктор всегда освобождает память, выделяемую объектом, даже если объект находится в недопустимом состоянии.

Тип данных элементов вектора, `T`, должен соответствовать следующим требованиям. В противном случае поведение `concurrent_vector` класс не определен.

- Деструктор не должны выдавать.

- Если конструктор по умолчанию или копирования создает, деструктор не должен объявляться с помощью `virtual` ключевое слово и он должен правильно работать с нулевыми памяти.

[[В начало](#top)]

##  <a name="queue"></a> Класс concurrent_queue

[Concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) класса, так же, как [std::queue](../../standard-library/queue-class.md) класса, позволяет получить доступ к его передним и задним элементам. `concurrent_queue` Класса позволяет параллельно безопасно постановки в очередь и вывода из очереди операций. `concurrent_queue` Класс также предоставляет поддержку итераторов, не нарушающих параллельность.

###  <a name="queue-differences"></a> Различия между concurrent_queue и очереди

`concurrent_queue` Класс сильно напоминает `queue` класса. Далее показано, где `concurrent_queue` отличается от `queue`:

- Поставить в очередь и вывода из очереди операций на `concurrent_queue` объект являются безопасными в режиме параллелизма.

- `concurrent_queue` Класс обеспечивает поддержку итераторов, не нарушающих параллельность.

- `concurrent_queue` Класс не предоставляет `front` или `pop` методы. `concurrent_queue` Класс заменяет эти методы, определив [try_pop](reference/concurrent-queue-class.md#try_pop) метод.

- `concurrent_queue` Класс не предоставляет `back` метод. Таким образом не может ссылаться на конец очереди.

- `concurrent_queue` Класс предоставляет [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) вместо метода `size` метод. `unsafe_size` Метод не является безопасным в режиме параллелизма.

###  <a name="queue-safety"></a> Параллельно безопасных операций

Все методы, ставящих в очередь для или вывода из очереди из `concurrent_queue` объект являются безопасными в режиме параллелизма.

В следующей таблице приведены распространенные `concurrent_queue` методы и операторы, которые являются безопасными в режиме параллелизма.

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

Несмотря на то что `empty` метод безопасен в режиме параллелизма, параллельная операция может привести к очереди для увеличения или уменьшения `empty` возвращает метод.

Ниже приведены наиболее распространенные методы и операторы, которые не являются безопасными в режиме параллелизма.

|||
|-|-|
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

###  <a name="queue-iterators"></a> Поддержка итераторов

`concurrent_queue` Предоставляет итераторы, которые не являются безопасными в режиме параллелизма. Мы рекомендуем использовать эти итераторы только для отладки.

Объект `concurrent_queue` элементов в прямом направлении только обходит итератор. В следующей таблице приведены операторы, что поддерживает каждый итератор.

|Оператор|Описание|
|--------------|-----------------|
|`operator++`|Переходит к следующему элементу в очереди. Этот оператор перегружен, чтобы предоставить семантику префиксный инкремент и после приращения.|
|`operator*`|Извлекает ссылку на текущий элемент.|
|`operator->`|Извлекает указатель на текущий элемент.|

[[В начало](#top)]

##  <a name="unordered_map"></a> Класс concurrent_unordered_map

[Concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) — класс ассоциативного контейнера, так же, как [std::unordered_map](../../standard-library/unordered-map-class.md) класс, управляющий последовательностью элементов типа переменнойдлины[std::pair\<const Key, Ty >](../../standard-library/pair-structure.md). Считать несортированное сопоставление словарь, который можно добавить пару "ключ-значение" в или поиска значений по ключу. Этот класс полезен в тех случаях, когда несколько потоков или задач, которые одновременно доступ общего контейнера, вставить в нее или обновить его.

Следующий пример показывает базовую структуру для с помощью `concurrent_unordered_map`. В этом примере вставляет ключи символ в диапазоне [«», «i»]. Поскольку порядок операций не определен, конечное значение для каждого ключа также не определен. Тем не менее можно безопасно для выполнения операций вставки в параллельном режиме.

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

Пример, использующий `concurrent_unordered_map` для осуществления карту и уменьшить количество операций в параллельном режиме, см. в разделе [как: Выполните карты и уменьшить объем операций в параллельном режиме](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).

###  <a name="map-differences"></a> Различия между concurrent_unordered_map и unordered_map

`concurrent_unordered_map` Класс сильно напоминает `unordered_map` класса. Далее показано, где `concurrent_unordered_map` отличается от `unordered_map`:

- `erase`, `bucket`, `bucket_count`, И `bucket_size` методов именованных `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, и `unsafe_bucket_size`, соответственно. `unsafe_` Соглашение об именовании указывает, что эти методы не являются безопасными в режиме параллелизма. Дополнительные сведения о безопасности параллельной обработки, см. в разделе [параллельно-безопасных операций](#map-safety).

- Операции вставки не делают недействительными существующие указатели или итераторы, а также их изменить порядок элементов, которые уже существует в сопоставлении. Вставка и обходить операций могут возникать одновременно.

- `concurrent_unordered_map` поддерживает пересылать только итерации.

- Вставки не недействительным и не обновляют итераторов, возвращенных `equal_range`. Вставки можно добавить в конец диапазона неравных элементов. Итератором begin равен элемента.

Чтобы избежать взаимоблокировки, метода не `concurrent_unordered_map` удерживает блокировку при вызове распределителя памяти, функции хэширования или другой пользовательский код. Кроме того необходимо убедиться, что хэш-функция всегда равно равно ключи совпадают. Лучшие функции хэширования равномерно распределять ключи на пространство кода хэш.

###  <a name="map-safety"></a> Параллельно безопасных операций

`concurrent_unordered_map` Класс позволяет параллельно безопасных операций вставки и доступа к элементу. Операции вставки не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются безопасными в режиме параллелизма. В следующей таблице показаны часто используемые `concurrent_unordered_map` методы и операторы, которые являются безопасными в режиме параллелизма.

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|

Несмотря на то что `count` метод может безопасно вызываться из одновременно выполняемых потоков, различными потоками может получать разные результаты, если новое значение одновременно вставить в контейнер.

Ниже приведены наиболее часто используемые методы и операторы, которые не являются безопасными в режиме параллелизма.

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[оператор=](reference/concurrent-unordered-map-class.md#operator_eq)

Помимо этих методов, любой метод, который начинается с `unsafe_` также не является безопасным в режиме параллелизма.

[[В начало](#top)]

##  <a name="unordered_multimap"></a> Класс concurrent_unordered_multimap

[Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) класс сильно напоминает `concurrent_unordered_map` класса за исключением того, что он допускает несколько значений для сопоставления с тем же ключом. Он также отличается от `concurrent_unordered_map` одним из следующих способов:

- [Concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert) метод возвращает итератор, указывающий вместо `std::pair<iterator, bool>`.

- `concurrent_unordered_multimap` Класс не предоставляет `operator[]` ни `at` метод.

Следующий пример показывает базовую структуру для с помощью `concurrent_unordered_multimap`. В этом примере вставляет ключи символ в диапазоне [«», «i»]. `concurrent_unordered_multimap` позволяет клавишу, чтобы иметь несколько значений.

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[В начало](#top)]

##  <a name="unordered_set"></a> Класс concurrent_unordered_set

[Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) класс сильно напоминает `concurrent_unordered_map` класса за исключением того, что он управляет значения, а не пары "ключ-значение". `concurrent_unordered_set` Класс не предоставляет `operator[]` ни `at` метод.

Следующий пример показывает базовую структуру для с помощью `concurrent_unordered_set`. В этом примере вставляет символ значения в диапазоне [«», «i»]. Можно безопасно для выполнения операций вставки в параллельном режиме.

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[В начало](#top)]

##  <a name="unordered_multiset"></a> Класс concurrent_unordered_multiset

[Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) класс сильно напоминает `concurrent_unordered_set` класса за исключением того, что он допускает повторяющиеся значения. Он также отличается от `concurrent_unordered_set` одним из следующих способов:

- [Concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert) метод возвращает итератор, указывающий вместо `std::pair<iterator, bool>`.

- `concurrent_unordered_multiset` Класс не предоставляет `operator[]` ни `at` метод.

Следующий пример показывает базовую структуру для с помощью `concurrent_unordered_multiset`. В этом примере вставляет символ значения в диапазоне [«», «i»]. `concurrent_unordered_multiset` допускает значения встречаться несколько раз.

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[В начало](#top)]

##  <a name="combinable"></a> Класс combinable

[Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс предоставляет многократно используемых, локальную для потока хранилище, которое позволяет выполнять детализированные вычисления и объединять их результаты в итоговый результат. Объект `combinable` можно рассматривать как переменную уменьшения.

`combinable` Класс может быть полезен, когда у вас есть ресурс, который является общим для нескольких потоков или задач. `combinable` Класс помогает исключить общее состояние, предоставляя доступ к общим ресурсам без блокировок. Таким образом этот класс предоставляет является альтернативой использованию механизм синхронизации, к примеру, семафор для синхронизации доступа к общим данным из нескольких потоков.

###  <a name="combinable-features"></a> Методы и функции

В следующей таблице показаны некоторые важные методы `combinable` класса. Дополнительные сведения обо всех `combinable` методы класса, см. в разделе [класс combinable](../../parallel/concrt/reference/combinable-class.md).

|Метод|Описание|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|Извлекает ссылку на локальную переменную, которой сопоставлен текущий контекст потока.|
|[clear](reference/combinable-class.md#clear)|Удаляет все локальные переменные потока из `combinable` объекта.|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Использует предоставленную функцию combine для создания окончательного значения из набора всех локальных вычислений потока.|

`combinable` Класс — это класс шаблона, который параметризуется по окончательному результату слияния. Если вызвать конструктор по умолчанию, `T` тип параметра шаблона должен иметь конструктор по умолчанию и конструктор копии. Если `T` тип параметров шаблона не имеет конструктор по умолчанию, вызовите перегруженную версию конструктора, который принимает в качестве параметра функции инициализации.

Дополнительные данные можно хранить `combinable` объекта после вызова метода [объединить](reference/combinable-class.md#combine) или [combine_each](reference/combinable-class.md#combine_each) методы. Можно также вызвать `combine` и `combine_each` несколько раз. Если в локальное значение не `combinable` изменения, объекта `combine` и `combine_each` методы дают одинаковый результат при каждом их вызове.

###  <a name="combinable-examples"></a> Примеры

Примеры об использовании `combinable` класса, см. в следующих разделах:

- [Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[В начало](#top)]

## <a name="related-topics"></a>См. также

[Практическое руководство. Использование параллельных контейнеров для повышения эффективности](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
В этой статье демонстрируется использование параллельных контейнеров для эффективного хранения и доступа к данным в параллельном режиме.

[Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
Демонстрируется использование `combinable` класса во избежание общее состояние и тем самым повысить производительность.

[Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
Демонстрируется использование `combine` функции для слияния наборов локального потока данных.

[Библиотека параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
Описывается Библиотека PPL, которая предоставляет императивную модель программирования, обеспечивающую масштабируемость и простота в использовании разработки параллельных приложений.

## <a name="reference"></a>Ссылка

[Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)

[Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)

[Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[Класс concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[Класс concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[Класс concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[Класс combinable](../../parallel/concrt/reference/combinable-class.md)
