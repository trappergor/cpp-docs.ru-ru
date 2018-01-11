---
title: "Параллельные контейнеры и объекты | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
caps.latest.revision: "34"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9159b9c8170ee73afd8bee5305506a842368a231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="parallel-containers-and-objects"></a>Параллельные контейнеры и объекты
Библиотека параллельных шаблонов (PPL) содержит несколько контейнеров и объектов, предоставляющих потокобезопасный доступ к своим элементам.  
  
 Объект *параллельном контейнере* предоставляет параллелизма безопасный доступ к наиболее важные операции. Функциональные возможности этих контейнеров аналогичны возможностям, предоставляемым стандартной библиотеки C++. Например [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) похож [std::vector](../../standard-library/vector-class.md) класса, за исключением того, что `concurrent_vector` позволяет добавлять элементы в параллельном режиме. Используйте параллельные контейнеры, при наличии параллельный код, требующий чтение и запись в тот же контейнер.  
  
 Объект *параллельный объект* совместно используется между компонентами. Процесс, который вычисляет состояние параллельного объекта в параллельном дает тот же результат, что и процесс, вычисляющий то же состояние последовательно. [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс является одним из примеров типа параллельных объектов. `combinable` Класс позволяет выполнять вычисления параллельно, а затем объединять результаты этих вычислений в конечный результат. Используйте параллельные объекты, если бы в противном случае использовать механизм синхронизации, например, мьютекс для синхронизации доступа к общей переменной или ресурсу.  
  
##  <a name="top"></a> Разделы  
 В этом разделе описываются следующие параллельные контейнеры и объекты подробно.  
  
 Параллельные контейнеры  
  
-   [Класс concurrent_vector](#ctor)  
  
    -   [Различия между concurrent_vector и вектор](#ctor)  
  
    -   [Параллельно безопасных операций](#ctor)  
  
    -   [Исключения безопасности](#ctor)  
  
-   [Класс concurrent_queue](#queue)  
  
    -   [Различия между concurrent_queue и очереди](#queue-differences)  
  
    -   [Параллельно безопасных операций](#queue-safety)  
  
    -   [Поддержка итераторов](#queue-iterators)  
  
-   [Класс concurrent_unordered_map](#unordered_map)  
  
    -   [Различия между concurrent_unordered_map и unordered_map](#map-differences)  
  
    -   [Параллельно безопасных операций](#map-safety)  
  
-   [Класс concurrent_unordered_multimap](#unordered_multimap)  
  
-   [Класс concurrent_unordered_set](#unordered_set)  
  
-   [Класс concurrent_unordered_multiset](#unordered_multiset)  
  
 Параллельные объекты  
  
-   [Класс combinable](#combinable)  
  
    -   [Методы и свойства](#combinable-features)  
  
    -   [Примеры](#combinable-examples)  
  
##  <a name="vector"></a>Класс concurrent_vector  
 [Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) класса является класс контейнера последовательности, так же, как [std::vector](../../standard-library/vector-class.md) класса, позволяет осуществлять доступ к его элементам. `concurrent_vector` Позволяет параллельно безопасно append и элемент доступа к операциям. Добавление операции не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются безопасными в режиме параллелизма.  
  
###  <a name="vector-differences"></a>Различия между concurrent_vector и вектор  
 `concurrent_vector` Напоминает класс `vector` класса. Сложность операции доступа итератора, доступ к элементу и добавления `concurrent_vector` объекта являются одинаковыми как для `vector` объекта. Далее показано, где `concurrent_vector` отличается от `vector`:  
  
-   Операции присоединения, доступ к элементу, доступа итератора и итератор обхода на `concurrent_vector` являются безопасными в режиме параллелизма.  
  
-   Добавлять элементы можно только в конце `concurrent_vector` объекта. `concurrent_vector` Класс не предоставляет `insert` метод.  
  
-   Объект `concurrent_vector` объект не использовал [семантику перемещения](../../cpp/rvalue-reference-declarator-amp-amp.md) при добавьте к нему.  
  

-   `concurrent_vector` Класс не предоставляет `erase` или `pop_back` методы. Как и в `vector`, используйте [снимите](reference/concurrent-vector-class.md#clear) метод, чтобы удалить все элементы из `concurrent_vector` объекта.  
  
-   `concurrent_vector` Не хранятся его элементы последовательно в памяти. Следовательно, нельзя использовать `concurrent_vector` класс всеми способами, которые можно использовать массив. Например, переменная с именем `v` типа `concurrent_vector`, выражение `&v[0]+2` выдает неопределенное поведение.  
  
-   `concurrent_vector` Класс определяет [grow_by](reference/concurrent-vector-class.md#grow_by) и [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) методы. Эти методы аналогичны [изменения размера](reference/concurrent-vector-class.md#resize) метода, за исключением того, что они являются безопасными в режиме параллелизма.  
  
-   Объект `concurrent_vector` объекта не переместить его элементов, добавьте к нему или изменить его размер. Благодаря этому существующие указатели и итераторы остаются действительными при выполнении параллельных операций.  
  
-   Среда выполнения не определяет специальную версию `concurrent_vector` для типа `bool`.  
  
###  <a name="vector-safety"></a>Параллельно безопасных операций  
 Все методы, добавляющие увеличить размер `concurrent_vector` объекта или доступа к элементу в `concurrent_vector` , являются безопасными в режиме параллелизма. Исключением из этого правила является `resize` метод.  
  
 В следующей таблице показаны распространенные `concurrent_vector` методы и операторы, которые являются безопасными в режиме параллелизма.  
  
||||  
|-|-|-|  

|[в](reference/concurrent-vector-class.md#at)|[окончания](reference/concurrent-vector-class.md#end)|[оператор &#91; &#93;](reference/concurrent-vector-class.md#operator_at)|  
|[Начать](reference/concurrent-vector-class.md#begin)|[передней](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|  
|[Назад](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|  
|[емкость](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|  
|[пустой](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[размер](reference/concurrent-vector-class.md#size)|  

  
 Операции, которые среда выполнения предоставляет для обеспечения совместимости с стандартной библиотеки C++, например, `reserve`, не являются безопасными в режиме параллелизма. Ниже приведены наиболее распространенные методы и операторы, которые не являются безопасными в режиме параллелизма.  
  
|||  
|-|-|  

|[Назначьте](reference/concurrent-vector-class.md#assign)|[резервирование](reference/concurrent-vector-class.md#reserve)|  
|[Очистить](reference/concurrent-vector-class.md#clear)|[изменения размера](reference/concurrent-vector-class.md#resize)|  
|[оператор =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|  
  
 Операции, изменяющие значение существующих элементов не параллельно безопасно. Использовать объект синхронизации, такие как [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md) объект для синхронизации параллельных чтения и операции записи в один и тот же элемент данных. Дополнительные сведения об объектах синхронизации см. в разделе [структуры данных синхронизации](../../parallel/concrt/synchronization-data-structures.md).  
  
 При преобразовании существующего кода, использующего `vector` использовать `concurrent_vector`, параллельные операции может привести к поведение приложения. Например, рассмотрим следующую программу, параллельно выполняет две задачи на `concurrent_vector` объекта. Первая задача добавляет дополнительные элементы для `concurrent_vector` объекта. Вторая задача вычисляет сумму всех элементов в тот же объект.  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]  
  

 Несмотря на то что `end` метод безопасен в режиме параллелизма, параллельный вызов [push_back](reference/concurrent-vector-class.md#push_back) значение, которое возвращается, вызывает метод `end` для изменения. Число элементов, проходящего через итератор не определен. Таким образом эта программа может привести к другой результат при каждом запуске.  
  
###  <a name="vector-exceptions"></a>Исключения безопасности  
 При операции увеличения или назначения выдает исключение, состояние `concurrent_vector` становится недействительным. Поведение `concurrent_vector` объект, который находится в недопустимом состоянии не определено, если не указано иное. Однако деструктор всегда освобождает память, выделяемую объектом, даже если объект находится в недопустимом состоянии.  
  
 Тип данных элементов вектора, `T`, должен соответствовать следующим требованиям. В противном случае поведение `concurrent_vector` определен класс.  
  
-   Деструктор не должны вызывать.  
  
-   Если конструктор по умолчанию или копирования создает, деструктор не должен объявляться с помощью `virtual` ключевое слово и он должен правильно работать с нулевыми памяти.  
  
 [[В начало](#top)]  
  
##  <a name="queue"></a>Класс concurrent_queue  
 [Concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) класса так же, как [std::queue](../../standard-library/queue-class.md) класса, можно получить доступ к его передним и задним элементам. `concurrent_queue` Класса позволяет параллельно безопасно постановки в очередь и вывода из очереди операций. `concurrent_queue` Класса также обеспечивает поддержку итераторов, не является безопасным в режиме параллелизма.  
  
###  <a name="queue-differences"></a>Различия между concurrent_queue и очереди  
 `concurrent_queue` Напоминает класс `queue` класса. Далее показано, где `concurrent_queue` отличается от `queue`:  
  
-   Поставить в очередь и вывода из очереди операций на `concurrent_queue` являются безопасными в режиме параллелизма.  
  
-   `concurrent_queue` Класс обеспечивает поддержку итераторов, не является безопасным в режиме параллелизма.  
  

-   `concurrent_queue` Класс не предоставляет `front` или `pop` методы. `concurrent_queue` Класс заменяет эти методы, определяя [try_pop](reference/concurrent-queue-class.md#try_pop) метод.  
  
-   `concurrent_queue` Класс не предоставляет `back` метод. Таким образом нельзя ссылаться на конец очереди.  
  
-   `concurrent_queue` Класс предоставляет [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) вместо метода `size` метод. `unsafe_size` Метод не является безопасным в режиме параллелизма.  

  
###  <a name="queue-safety"></a>Параллельно безопасных операций  
 Все методы, постановки в очередь для или вывода из очереди из `concurrent_queue` являются безопасными в режиме параллелизма.  
  
 В следующей таблице показаны распространенные `concurrent_queue` методы и операторы, которые являются безопасными в режиме параллелизма.  
  
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


  
###  <a name="queue-iterators"></a>Поддержка итераторов  
 `concurrent_queue` Предоставляет итераторы, которые не являются безопасными в режиме параллелизма. Мы рекомендуем использовать эти итераторы, только для отладки.  
  
 Объект `concurrent_queue` итератора проходит элементы в прямом направлении только. Ниже приведены операторы, что поддерживаются каждым итератором.  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[оператор++](http://msdn.microsoft.com/en-us/4cfdd07e-927a-42f8-aaa0-d6881687f413)|Переходит к следующему элементу в очереди. Этот оператор перегружен, чтобы предоставить семантику префиксный инкремент и после приращения.|  
|[оператор*](http://msdn.microsoft.com/en-us/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|Извлекает ссылку на текущий элемент.|  
|[оператор>](http://msdn.microsoft.com/en-us/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|Извлекает указатель на текущий элемент.|  
  
 [[В начало](#top)]  
  
##  <a name="unordered_map"></a>Класс concurrent_unordered_map  
 [Гиперссылка «file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default \\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622» concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) класс Класс ассоциативного контейнера, так же, как [std::unordered_map](../../standard-library/unordered-map-class.md) класс, управляющий последовательностью элементов типа переменной длины [std::pair\<const ключ, за этот год >](../../standard-library/pair-structure.md). Считаете несортированное сопоставление словарь, который можно добавить пару "ключ-значение" для или поиска значений по ключу. Данный класс удобно при наличии нескольких потоков или задач, которые должны одновременно доступ к общей контейнеру, вставьте в него или обновить.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_map`. В этом примере вставляет клавиши со знаками в диапазоне [«», «i»]. Так как порядок операций не определена, конечное значение для каждого ключа также не определена. Тем не менее можно безопасно для выполнения операций вставки в параллельном режиме.  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]  
  
 Пример, использующий `concurrent_unordered_map` для осуществления карты и уменьшить операции в параллельном режиме, в разделе [как: выполнять сопоставление и уменьшить операций параллельно](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md).  
  
###  <a name="map-differences"></a>Различия между concurrent_unordered_map и unordered_map  
 `concurrent_unordered_map` Напоминает класс `unordered_map` класса. Далее показано, где `concurrent_unordered_map` отличается от `unordered_map`:  
  
-   `erase`, `bucket`, `bucket_count`, И `bucket_size` методов, названных `unsafe_erase`, `unsafe_bucket`, `unsafe_bucket_count`, и `unsafe_bucket_size`соответственно. `unsafe_` Указывает соглашение об именовании, эти методы не являются безопасными в режиме параллелизма. Дополнительные сведения о безопасности параллельной обработки см. в разделе [параллельно-безопасных операций](#map-safety).  
  
-   Операции вставки не делают недействительными существующие указатели или итераторы, а также их изменить порядок элементов, которые уже существуют в схеме. Вставка и проходят через параллельное выполнение операций.  
  
-   `concurrent_unordered_map`поддерживает пересылать только итерации.  
  
-   Вставки не приводят к недействительности или обновить итераторы, которые возвращаются по `equal_range`. Вставка добавления неравных элементов в конец диапазона. Итератором begin равен элемент.  
  
 Чтобы избежать взаимоблокировки метода не `concurrent_unordered_map` удерживает блокировку, при вызове распределитель памяти, хэш-функции или другой пользовательский код. Кроме того необходимо убедиться, что хэш-функции всегда проверяет ключи равны, то же значение. Наиболее хэш-функции распределяют ключи равномерно пространство кода хэш.  
  
###  <a name="map-safety"></a>Параллельно безопасных операций  
 `concurrent_unordered_map` Класс позволяет параллельно безопасных операций вставки и доступа к элементу. Операции вставки, не делают недействительными существующие указатели или итераторы. Операции доступа и обхода итератора также являются безопасными в режиме параллелизма. В следующей таблице показаны часто используемые `concurrent_unordered_map` методы и операторы, которые являются безопасными в режиме параллелизма.  
  
|||||  
|-|-|-|-|  
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|  
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|  
  
 Несмотря на то что `count` метод может безопасно вызываться из одновременно запущенных потоков, разных потоков могут получать разные результаты, если новое значение одновременно вставить в контейнер.  
  
 В следующей таблице показаны часто используемые методы и операторы, которые не являются безопасными в режиме параллелизма.  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[оператор=](reference/concurrent-unordered-map-class.md#operator_eq) 


  
 Помимо этих методов, любой метод, который начинается с `unsafe_` также не является безопасным в режиме параллелизма.  
  
 [[В начало](#top)]  
  
##  <a name="unordered_multimap"></a>Класс concurrent_unordered_multimap  
 [Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md) напоминает класс `concurrent_unordered_map` класса, за исключением того, что он допускает несколько значений для сопоставления с тем же ключом. Он также отличается от `concurrent_unordered_map` одним из следующих способов:  
  
-   [Concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert) метод возвращает итератор вместо `std::pair<iterator, bool>`.  

  
-   `concurrent_unordered_multimap` Класс не предоставляет `operator[]` ни `at` метод.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_multimap`. В этом примере вставляет клавиши со знаками в диапазоне [«», «i»]. `concurrent_unordered_multimap`позволяет иметь несколько значений ключа.  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]  
  
 [[В начало](#top)]  
  
##  <a name="unordered_set"></a>Класс concurrent_unordered_set  
 [Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md) напоминает класс `concurrent_unordered_map` класса, за исключением того, что он управляет значений, а не пары "ключ-значение". `concurrent_unordered_set` Класс не предоставляет `operator[]` ни `at` метод.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_set`. В этом примере вставляет символ значения в диапазоне [«», «i»]. Безопасно для выполнения операций вставки в параллельном режиме.  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]  
  
 [[В начало](#top)]  
  
##  <a name="unordered_multiset"></a>Класс concurrent_unordered_multiset  
 [Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md) напоминает класс `concurrent_unordered_set` класса, за исключением того, что позволяет повторяющиеся значения. Он также отличается от `concurrent_unordered_set` одним из следующих способов:  
  

-   [Concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert) метод возвращает итератор вместо `std::pair<iterator, bool>`.  

  
-   `concurrent_unordered_multiset` Класс не предоставляет `operator[]` ни `at` метод.  
  
 В следующем примере показана базовая структура для использования `concurrent_unordered_multiset`. В этом примере вставляет символ значения в диапазоне [«», «i»]. `concurrent_unordered_multiset`включает значение возникает несколько раз.  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]  
  
 [[В начало](#top)]  
  
##  <a name="combinable"></a>Класс combinable  
 [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md) класс предоставляет хранилище для повторного использования, локальных для потока, которое позволяет выполнять детализированные вычисления и объединять их в общий результат. Объект `combinable` можно рассматривать как переменную уменьшения.  
  
 `combinable` Класс удобен при наличии ресурсов, являющихся общими для нескольких потоков или задач. `combinable` Класс помогает исключить состояние с общим доступом, предоставляя доступ к общим ресурсам без блокировок. Таким образом этот класс предоставляет альтернативы механизм синхронизации, например, мьютекс для синхронизации доступа к общим данным из нескольких потоков.  
  
###  <a name="combinable-features"></a>Методы и свойства  
 В следующей таблице показаны некоторые важные методы `combinable` класса. Дополнительные сведения обо всех `combinable` методы класса см. в разделе [класс combinable](../../parallel/concrt/reference/combinable-class.md).  
  
|Метод|Описание:|  
|------------|-----------------|  
|[локальные](reference/combinable-class.md#local)|Извлекает ссылку на локальную переменную, связанный с текущим контекстом потока.|  
|[clear](reference/combinable-class.md#clear)|Удаляет все локальные переменные потока из `combinable` объекта.|  
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|Использует предоставленную функцию combine для создания окончательного значения из набора всех вычислений, локальных для потока.|  
  
 `combinable` Класс — это класс шаблона, который параметризуется по окончательному результату слияния. Если вызвать конструктор по умолчанию `T` тип параметра шаблона должен иметь конструктор по умолчанию и конструктор копии. Если `T` тип параметра шаблона не имеет конструктора по умолчанию, вызовите перегруженную версию конструктора, принимающего ошибки инициализации функции в качестве параметра.  
  
 Для хранения дополнительных данных в `combinable` после вызова метода [объединение](reference/combinable-class.md#combine) или [combine_each](reference/combinable-class.md#combine_each) методы. Можно также вызвать `combine` и `combine_each` методы несколько раз. Если в локальное значение не `combinable` изменяется, `combine` и `combine_each` методы дают одинаковый результат при каждом их вызове.  
  
###  <a name="combinable-examples"></a> Примеры  
 Примеры об использовании `combinable` класса, в следующих разделах:  
  
-   [Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[В начало](#top)]  
  
## <a name="related-topics"></a>См. также  
 [Практическое руководство. Использование параллельных контейнеров для повышения эффективности](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 Демонстрирует использование параллельных контейнеров для эффективного хранения и доступа к данным в параллельном режиме.  
  
 [Практическое руководство. Использование класса combinable для повышения производительности](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 Показано, как использовать `combinable` класса, чтобы исключить состояние с общим и тем самым повысить производительность.  
  
 [Практическое руководство. Использование класса combinable для комбинирования наборов](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 Показано, как использовать `combine` функцию для объединения наборов данных, локальных для потока.  
  
 [Библиотека параллельных шаблонов (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 Описывается Библиотека PPL, которая предоставляет императивную модель программирования, обеспечивающую масштабируемость и простота удобство разработки параллельных приложений.  
  
## <a name="reference"></a>Ссылка  
 [Класс concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [Класс concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [Класс concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [Класс concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [Класс concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [Класс concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [Класс combinable](../../parallel/concrt/reference/combinable-class.md)
