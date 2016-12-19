---
title: "Параллельные контейнеры и объекты | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "параллельные объекты"
  - "параллельные контейнеры"
  - "параллельные контейнеры"
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Параллельные контейнеры и объекты
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Библиотека параллельных шаблонов (PPL) содержит несколько контейнеров и объектов, предоставляющих потокобезопасный доступ к элементам.  
  
 A *Параллельный контейнер* предоставляет параллелизма безопасный доступ к наиболее важные операции. Функциональные возможности этих контейнеров аналогичны возможностям, предоставляемые библиотеки стандартных шаблонов (STL). Например [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) напоминает класс [std::vector](vector%20Class.md) класса, за исключением того, что `concurrent_vector` позволяет добавлять элементы в параллельном режиме. Параллельные контейнеры рекомендуется используйте при наличии параллельный код, требующий чтение и запись в тот же контейнер.  
  
 A *Параллельный объект* совместно используется между компонентами. Процесс, вычисляющий состояние параллельного объекта в параллельном дает тот же результат, что и процесс, вычисляющий то же состояние последовательно.  [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс является одним из примеров типа параллельных объектов.  `combinable` Класс позволяет выполнять вычисления параллельно, а затем объединять результаты этих вычислений в конечный результат. Параллельные объекты следует используйте, если бы в противном случае использовать механизм синхронизации, например мьютекс для синхронизации доступа к общей переменной или ресурсу.  
  
##  <a name="a-nametopa-sections"></a><a name="top"></a> Разделы  
 В этом разделе описываются следующие параллельные контейнеры и объекты подробно.  
  
 Параллельные контейнеры  
  
-   [Класс concurrent_vector](#vector)  
  
    -   [Различия между concurrent_vector и vector](#vector-differences)  
  
    -   [Параллельно безопасных операций](#vector-safety)  
  
    -   [Исключения безопасности](#vector-exceptions)  
  
-   [Класс concurrent_queue](#queue)  
  
    -   [Различия между concurrent_queue и очередей](#queue-differences)  
  
    -   [Параллельно безопасных операций](#queue-safety)  
  
    -   [Поддержку итераторов](#queue-iterators)  
  
-   [Класс concurrent_unordered_map](#unordered_map)  
  
    -   [Различия между concurrent_unordered_map и unordered_map](#map-differences)  
  
    -   [Параллельно безопасных операций](#map-safety)  
  
-   [Класс concurrent_unordered_multimap](#unordered_multimap)  
  
-   [Класс concurrent_unordered_set](#unordered_set)  
  
-   [Класс concurrent_unordered_multiset](#unordered_multiset)  
  
 Параллельные объекты  
  
-   [Класс combinable](#combinable)  
  
    -   [Методы и функции](#combinable-features)  
  
    -   [Примеры](#combinable-examples)  
  
##  <a name="a-namevectora-concurrentvector-class"></a><a name="vector"></a> Класс concurrent_vector  
  [Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класса является класс контейнера последовательности, как [std::vector](vector%20Class.md) класса, позволяет осуществлять доступ к его элементам.  `concurrent_vector` Позволяет параллельно безопасно добавить и элемент доступа к операциям. Добавление операции не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются безопасными в режиме параллелизма.  
  
###  <a name="a-namevector-differencesa-differences-between-concurrentvector-and-vector"></a><a name="vector-differences"></a> Различия между concurrent_vector и vector  
  `concurrent_vector` Напоминает класс `vector` класса. Сложность добавления, доступа к элементу и операции доступа к итератору на `concurrent_vector` объекта являются одинаковыми как для `vector` объекта. Далее показано, где `concurrent_vector` отличается от `vector`:  
  
-   Доступ к элементу, доступа к итератору, операции присоединения и итератора обхода на `concurrent_vector` являются безопасными в режиме параллелизма.  
  
-   Добавлять элементы можно только в конце `concurrent_vector` объекта.  `concurrent_vector` Класс не предоставляет `insert` метод.  
  
-   Объект `concurrent_vector` объект не использовал [семантику перемещения](../../cpp/rvalue-reference-declarator-amp-amp.md) при добавлении к нему.  
  
-    `concurrent_vector` Класс не предоставляет `erase` или `pop_back` методы. Как и в `vector`, используйте [снимите](../Topic/concurrent_vector::clear%20Method.md) метод, чтобы удалить все элементы из `concurrent_vector` объекта.  
  
-    `concurrent_vector` Не хранятся элементы последовательно в памяти. Следовательно, нельзя использовать `concurrent_vector` класса во всех отношениях, что можно использовать массив. Например, переменная с именем `v` типа `concurrent_vector`, выражение `&v[0]+2` выдает неопределенное поведение.  
  
-    `concurrent_vector` Класс определяет [grow_by](../Topic/concurrent_vector::grow_by%20Method.md) и [grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md) методы. Эти методы аналогичны [изменения размера](../Topic/concurrent_vector::resize%20Method.md) метода, за исключением того, что они являются безопасными в режиме параллелизма.  
  
-   A `concurrent_vector` объекта не переместить его элементов, добавьте к нему или изменить его размер. Благодаря этому существующие указатели и итераторы остаются действительными при выполнении параллельных операций.  
  
-   Среда выполнения не определяет специальную версию `concurrent_vector` для типа `bool`.  
  
###  <a name="a-namevector-safetya-concurrency-safe-operations"></a><a name="vector-safety"></a> Параллельно безопасных операций  
 Все методы, добавляющие увеличить размер `concurrent_vector` объекта или доступа к элементу в `concurrent_vector` являются безопасными в режиме параллелизма. Исключением из этого правила является `resize` метод.  
  
 В следующей таблице приведены распространенные `concurrent_vector` методы и операторы, которые являются безопасными в режиме параллелизма.  
  
||||  
|-|-|-|  
|[в](../Topic/concurrent_vector::at%20Method.md)|[конец](../Topic/concurrent_vector::end%20Method.md)|[оператор &#91; &#93;](../Topic/concurrent_vector::operatorOperator.md)|  
|[начать](../Topic/concurrent_vector::begin%20Method.md)|[передний план](../Topic/concurrent_vector::front%20Method.md)|[push_back](../Topic/concurrent_vector::push_back%20Method.md)|  
|[Назад](../Topic/concurrent_vector::back%20Method.md)|[grow_by](../Topic/concurrent_vector::grow_by%20Method.md)|[rbegin](../Topic/concurrent_vector::rbegin%20Method.md)|  
|[емкость](../Topic/concurrent_vector::capacity%20Method.md)|[grow_to_at_least](../Topic/concurrent_vector::grow_to_at_least%20Method.md)|[rend](../Topic/concurrent_vector::rend%20Method.md)|  
|[пустой](../Topic/concurrent_vector::empty%20Method.md)|[max_size](../Topic/concurrent_vector::max_size%20Method.md)|[размер](../Topic/concurrent_vector::size%20Method.md)|  
  
 Операции, которые среда выполнения предоставляет для обеспечения совместимости с STL, например, `reserve`, не являются безопасными в режиме параллелизма. Ниже приведены наиболее распространенные методы и операторы, которые не являются безопасными в режиме параллелизма.  
  
|||  
|-|-|  
|[Назначение](../Topic/concurrent_vector::assign%20Method.md)|[Резерв](../Topic/concurrent_vector::reserve%20Method.md)|  
|[Очистка](../Topic/concurrent_vector::clear%20Method.md)|[Изменение размеров](../Topic/concurrent_vector::resize%20Method.md)|  
|[оператор =](../Topic/concurrent_vector::operator=%20Operator.md)|[shrink_to_fit](../Topic/concurrent_vector::shrink_to_fit%20Method.md)|  
  
 Операции, изменяющие значение существующих элементов не являются безопасными в режиме параллелизма. Используйте объект синхронизации, например [reader_writer_lock](../Topic/reader_writer_lock%20Class.md) объект для синхронизации параллельных чтения и записи операций один и тот же элемент данных. Дополнительные сведения об объектах синхронизации см. в разделе [структуры данных синхронизации](../Topic/Synchronization%20Data%20Structures.md).  
  
 При преобразовании существующего кода, использующего `vector` использовать `concurrent_vector`, одновременных операций может привести к поведение приложения. Например, рассмотрим следующую программу, параллельно выполняет две задачи на `concurrent_vector` объект. Первая задача добавляет дополнительные элементы для `concurrent_vector` объекта. Вторая задача вычисляет сумму всех элементов в тот же объект.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_1.cpp)]  
  
 Хотя `end` метод безопасен в режиме параллелизма, параллельный вызов [push_back](../Topic/concurrent_vector::push_back%20Method.md) значение, которое возвращается, вызывает метод `end` для изменения. Число элементов, проходящего через итератор не определено. Таким образом эта программа может создавать различные результаты при каждом его запуске.  
  
###  <a name="a-namevector-exceptionsa-exception-safety"></a><a name="vector-exceptions"></a> Исключения безопасности  
 При выполнении операции увеличения или назначения выдает исключение, состояние `concurrent_vector` объект становится недействительным. Поведение `concurrent_vector` объекта, находящегося в недопустимое состояние не определено, если не указано иное. Однако деструктор всегда освобождает память, выделяемую объектом, даже если объект находится в недопустимом состоянии.  
  
 Тип данных элементов класса vector, `T`, должен соответствовать следующим требованиям. В противном случае — поведение `concurrent_vector` определен класс.  
  
-   Деструктор не должно вызвать исключение.  
  
-   Если конструктор по умолчанию или копирования создает, деструктор не должен объявляться с помощью `virtual` ключевое слово и он должен правильно работать с нулевыми памяти.  
  
 [[В начало](#top)]  
  
##  <a name="a-namequeuea-concurrentqueue-class"></a><a name="queue"></a> Класс concurrent_queue  
  [Concurrency::concurrent_queue](../Topic/concurrent_queue%20Class.md) класса так же, как [std::queue](../../standard-library/queue-class.md) класса, можно получить доступ к его передним и задним элементам.  `concurrent_queue` Класса позволяет параллельно безопасно постановки в очередь и удаления из очереди операций.  `concurrent_queue` Класс также предоставляет поддержку итераторов, не является безопасным в режиме параллелизма.  
  
###  <a name="a-namequeue-differencesa-differences-between-concurrentqueue-and-queue"></a><a name="queue-differences"></a> Различия между concurrent_queue и очередей  
  `concurrent_queue` Напоминает класс `queue` класса. Далее показано, где `concurrent_queue` отличается от `queue`:  
  
-   Постановка в очередь и удаления из очереди операций на `concurrent_queue` являются безопасными в режиме параллелизма.  
  
-    `concurrent_queue` Класс обеспечивает поддержку итераторов, не является безопасным в режиме параллелизма.  
  
-    `concurrent_queue` Класс не предоставляет `front` или `pop` методы.  `concurrent_queue` Класс заменяет эти методы, определив [try_pop](../Topic/concurrent_queue::try_pop%20Method.md) метод.  
  
-    `concurrent_queue` Класс не предоставляет `back` метод. Следовательно нельзя ссылаться на конец очереди.  
  
-    `concurrent_queue` Класс предоставляет [unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md) вместо метода `size` метод.  `unsafe_size` Метод не является безопасным в режиме параллелизма.  
  
###  <a name="a-namequeue-safetya-concurrency-safe-operations"></a><a name="queue-safety"></a> Параллельно безопасных операций  
 Все методы, помещающие элементы в очередь или удаляющие их из очереди `concurrent_queue` являются безопасными в режиме параллелизма.  
  
 В следующей таблице приведены распространенные `concurrent_queue` методы и операторы, которые являются безопасными в режиме параллелизма.  
  
|||  
|-|-|  
|[пустой](../Topic/concurrent_queue::empty%20Method.md)|[Push](../Topic/concurrent_queue::push%20Method.md)|  
|[get_allocator](../Topic/concurrent_queue::get_allocator%20Method.md)|[try_pop](../Topic/concurrent_queue::try_pop%20Method.md)|  
  
 Хотя `empty` метод безопасен в режиме параллелизма, параллельная операция может привести к очереди для увеличения или уменьшения `empty` возвращает метод.  
  
 Ниже приведены наиболее распространенные методы и операторы, которые не являются безопасными в режиме параллелизма.  
  
|||  
|-|-|  
|[Очистка](../Topic/concurrent_queue::clear%20Method.md)|[unsafe_end](../Topic/concurrent_queue::unsafe_end%20Method.md)|  
|[unsafe_begin](../Topic/concurrent_queue::unsafe_begin%20Method.md)|[unsafe_size](../Topic/concurrent_queue::unsafe_size%20Method.md)|  
  
###  <a name="a-namequeue-iteratorsa-iterator-support"></a><a name="queue-iterators"></a> Поддержку итераторов  
  `concurrent_queue` Предоставляет итераторы, которые не являются безопасными в режиме параллелизма. Мы рекомендуем использовать эти итераторы только для отладки.  
  
 A `concurrent_queue` итератор проходит элементы в прямом направлении только. В следующей таблице показаны операторы, поддерживаются каждым итератором.  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[Operator ++](http://msdn.microsoft.com/ru-ru/4cfdd07e-927a-42f8-aaa0-d6881687f413)|Переходит к следующему элементу в очереди. Этот оператор перегружается для предоставления семантику префиксного и постфиксного приращений.|  
|[оператор *](http://msdn.microsoft.com/ru-ru/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|Извлекает ссылку на текущий элемент.|  
|[оператор ->](http://msdn.microsoft.com/ru-ru/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|Извлекает указатель на текущий элемент.|  
  
 [[В начало](#top)]  
  
##  <a name="a-nameunorderedmapa-concurrentunorderedmap-class"></a><a name="unordered_map"></a> Класс concurrent_unordered_map  
  [ГИПЕРССЫЛКА «file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default\\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622» concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) класс является классом ассоциативного контейнера, как [std::unordered_map](../../standard-library/unordered-map-class.md) класс, управляющий последовательностью элементов типа переменной длины [std::pair \< const ключ, Ty >](../../standard-library/pair-structure.md). Считать неупорядоченном сопоставлении словарь, который можно добавить пару "ключ-значение" в или искать значение по ключу. Данный класс полезен при наличии нескольких потоков или задач, которые содержат одновременно доступ общий контейнер, вставьте в него или его обновления.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_map`. В этом примере вставляет символ ключи в диапазоне [«», «i»]. Поскольку порядок операций не определен, конечное значение для каждого ключа также непредсказуемо. Тем не менее можно безопасно выполнять операции вставки в параллельном режиме.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_2.cpp)]  
  
 Пример, использующий `concurrent_unordered_map` для выполнения операций сопоставления и редукции параллельно, в разделе [как: выполнение сопоставления и уменьшения параллельные операции](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
###  <a name="a-namemap-differencesa-differences-between-concurrentunorderedmap-and-unorderedmap"></a><a name="map-differences"></a> Различия между concurrent_unordered_map и unordered_map  
  `concurrent_unordered_map` Напоминает класс `unordered_map` класса. Далее показано, где `concurrent_unordered_map` отличается от `unordered_map`:  
  
-    `erase`, `bucket`, `bucket_count`, И `bucket_size` методы называются `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, и `unsafe_bucket_size`, соответственно.  `unsafe_` Соглашение об именах указывает, что эти методы не параллельно безопасно. Дополнительные сведения о безопасности параллельной обработки см. в разделе [параллельно-безопасных операций](#map-safety).  
  
-   Операции вставки не делают недействительными существующие указатели и итераторы, а также их изменить порядок элементов, которые уже существуют в схеме. Вставка и просматривать параллельно выполняются операции.  
  
-   `concurrent_unordered_map` поддерживает пересылку только итерации.  
  
-   Вставка недействительной и не обновлять итераторы, возвращаемые `equal_range`. Вставка добавления неравных элементов в конец диапазона. Итератором begin равно элемента.  
  
 Чтобы избежать взаимоблокировки, метода не `concurrent_unordered_map` удерживает блокировку при вызове выделения памяти, функции хэширования или другой пользовательский код. Кроме того необходимо убедиться, что хэш-функции всегда равно равно ключи, то же значение. Лучшие функции хэширования распределение ключей равномерно места кода хэш.  
  
###  <a name="a-namemap-safetya-concurrency-safe-operations"></a><a name="map-safety"></a> Параллельно безопасных операций  
  `concurrent_unordered_map` Класс позволяет параллельно безопасных операций вставки и доступа к элементу. Операции вставки не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются безопасными в режиме параллелизма. В следующей таблице показаны часто используемые `concurrent_unordered_map` методы и операторы, которые являются безопасными в режиме параллелизма.  
  
|||||  
|-|-|-|-|  
|[в](../Topic/concurrent_unordered_map::at%20Method.md)|`count`|`find`|[key_eq](../Topic/concurrent_unordered_map::key_eq%20Method.md)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[оператор &#91; &#93;](../Topic/concurrent_unordered_map::operatorOperator.md)|  
|`cend`|`equal_range`|[Вставка](../Topic/concurrent_unordered_map::insert%20Method.md)|`size`|  
  
 Хотя `count` метод может безопасно вызываться из одновременно выполняющихся потоков, различными потоками может получать разные результаты, если новое значение одновременно вставлены в контейнере.  
  
 В следующей таблице показаны часто используемые методы и операторы, которые не являются безопасными в режиме параллелизма.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[оператор =](../Topic/concurrent_unordered_map::operator=%20Operator.md)|[Переключение](../Topic/concurrent_unordered_map::swap%20Method.md)|  
  
 Помимо этих методов, любой метод, который начинается с `unsafe_` также не является безопасным в режиме параллелизма.  
  
 [[В начало](#top)]  
  
##  <a name="a-nameunorderedmultimapa-concurrentunorderedmultimap-class"></a><a name="unordered_multimap"></a> Класс concurrent_unordered_multimap  
  [Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) напоминает класс `concurrent_unordered_map` класса, за исключением того, что он допускает несколько значений для сопоставления с тем же ключом. Он также отличается от `concurrent_unordered_map` следующим образом:  
  
-    [Concurrent_unordered_multimap::insert](../Topic/concurrent_unordered_multimap::insert%20Method.md) метод возвращает итератор, а не `std::pair<iterator, bool>`.  
  
-    `concurrent_unordered_multimap` Класс не предоставляет `operator[]` ни `at` метод.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_multimap`. В этом примере вставляет символ ключи в диапазоне [«», «i»]. `concurrent_unordered_multimap` позволяет иметь несколько значений ключа.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_3.cpp)]  
  
 [[В начало](#top)]  
  
##  <a name="a-nameunorderedseta-concurrentunorderedset-class"></a><a name="unordered_set"></a> Класс concurrent_unordered_set  
  [Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) напоминает класс `concurrent_unordered_map` класса, за исключением того, что он управляет значений вместо пар ключ-значение.  `concurrent_unordered_set` Класс не предоставляет `operator[]` ни `at` метод.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_set`. В этом примере вставляет символ значения в диапазоне [«», «i»]. Безопасно для выполнения операций вставки в параллельном режиме.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/CPP/parallel-containers-and-objects_4.cpp)]  
  
 [[В начало](#top)]  
  
##  <a name="a-nameunorderedmultiseta-concurrentunorderedmultiset-class"></a><a name="unordered_multiset"></a> Класс concurrent_unordered_multiset  
  [Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) напоминает класс `concurrent_unordered_set` класса, за исключением того, что позволяет повторяющиеся значения. Он также отличается от `concurrent_unordered_set` следующим образом:  
  
-    [Concurrent_unordered_multiset::insert](../Topic/concurrent_unordered_multiset::insert%20Method.md) метод возвращает итератор, а не `std::pair<iterator, bool>`.  
  
-    `concurrent_unordered_multiset` Класс не предоставляет `operator[]` ни `at` метод.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_multiset`. В этом примере вставляет символ значения в диапазоне [«», «i»]. `concurrent_unordered_multiset` включает значение возникает несколько раз.  
  
 [!CODE [concrt-unordered-multiset#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-unordered-multiset#1)]  
  
 [[В начало](#top)]  
  
##  <a name="a-namecombinablea-combinable-class"></a><a name="combinable"></a> Класс combinable  
  [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс предоставляет хранилища для повторного использования, локальную для потока, позволяющий выполнять детализированные вычисления и объединять их результаты в общий результат. Объект `combinable` можно рассматривать как переменную уменьшения.  
  
  `combinable` Класс полезен при наличии ресурсов, которое является общим для нескольких потоков или задач.  `combinable` Класс помогает исключить состояние с общим доступом, предоставляя доступ к общим ресурсам без блокировок. Таким образом этот класс предоставляет альтернативы использованию механизм синхронизации, например мьютекс для синхронизации доступа к общим данным из нескольких потоков.  
  
###  <a name="a-namecombinable-featuresa-methods-and-features"></a><a name="combinable-features"></a> Методы и функции  
 В следующей таблице показаны некоторые важные методы `combinable` класса. Дополнительные сведения обо всех `combinable` методы класса см. в разделе [класса combinable](../../parallel/concrt/reference/combinable-class.md).  
  
|Метод|Описание|  
|------------|-----------------|  
|[локальный](../Topic/combinable::local%20Method.md)|Извлекает ссылку на локальную переменную, которой сопоставлен текущий контекст потока.|  
|[Очистка](../Topic/combinable::clear%20Method.md)|Удаляет все локальные переменные потока из `combinable` объекта.|  
|[Объединение](../Topic/combinable::combine%20Method.md)<br /><br /> [combine_each](../Topic/combinable::combine_each%20Method.md)|Использует предоставленную функцию combine для создания окончательного значения из набора всех локальных вычислений потока.|  
  
  `combinable` Класс — это класс шаблона, который параметризуется по окончательному результату слияния. Если вызывается конструктор по умолчанию, `T` тип параметра шаблона должен иметь конструктор по умолчанию и конструктор копии. Если `T` тип параметра шаблона не имеет конструктор по умолчанию, вызовите перегруженную версию конструктора, принимающий в качестве параметра функции инициализации.  
  
 Можно хранить дополнительные данные в `combinable` объекта после вызова [объединение](../Topic/combinable::combine%20Method.md) или [combine_each](../Topic/combinable::combine_each%20Method.md) методы. Можно также вызвать `combine` и `combine_each` методов несколько раз. Если в локальное значение не `combinable` изменения, объекта `combine` и `combine_each` методы дают одинаковый результат каждый раз, когда они вызываются.  
  
###  <a name="a-namecombinable-examplesa-examples"></a><a name="combinable-examples"></a> Примеры  
 Примеры способов использования `combinable` класса, в следующих разделах:  
  
-   [Практическое руководство: использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [Практическое руководство: использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[В начало](#top)]  
  
## <a name="related-topics"></a>Связанные разделы  
 [Практическое руководство: использование параллельных контейнеров для повышения эффективности](../Topic/How%20to:%20Use%20Parallel%20Containers%20to%20Increase%20Efficiency.md)  
 Демонстрируется использование параллельных контейнеров для эффективного хранения и доступа к данным в параллельном режиме.  
  
 [Практическое руководство: использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 Показано, как использовать `combinable` класса, чтобы исключить состояние с общим доступом и тем самым повысить производительность.  
  
 [Практическое руководство: использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 Показано, как использовать `combine` функции для слияния локальных наборов потока данных.  
  
 [Библиотека параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Описывает библиотеку PPL, которая предоставляет императивную модель программирования, обеспечивающую масштабируемость и простота использования разработки параллельных приложений.  
  
## <a name="reference"></a>Ссылка  
 [Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [Класс concurrent_queue](../Topic/concurrent_queue%20Class.md)  
  
 [Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [Класс concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [Класс concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [Класс concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [Класс combinable](../../parallel/concrt/reference/combinable-class.md)
