---
title: "&lt;allocators&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::<allocators>"
  - "allocators/stdext::allocators"
  - "<allocators>"
  - "stdext.<allocators>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocators - заголовок"
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;allocators&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет несколько шаблонов, упрощающих выделение и освобождение блоков памяти для контейнеров на основе узлов.  
  
## Синтаксис  
  
```  
#include <allocators>  
```  
  
## Заметки  
 \<allocators\> Заголовок содержит 6 шаблонов распределителя, которые можно использовать для выделения стратегии управления памятью для контейнеров на основе узлов.  Для использования с этими шаблонами он также предоставляет несколько различных фильтров синхронизации настраивать стратегии управления памятью для различных различным схемам многопоточности \(включая отсутствует\).  Соответствия стратегии управления памятью в известным шаблоны потребления памяти и требованиями к синхронизации, определенного приложения часто может увеличивать или уменьшать скорость общие требования к памяти приложения.  
  
 Шаблоны распределителя реализованы с многоразовыми компонентами, которые можно настраивать или заменить, чтобы предоставить дополнительные стратегии управления памятью.  
  
 Контейнеры после внесения зависимости в стандартной библиотеке C\+\+ \(C std::list, std::set, std::multiset, std::map и std::multimap\) хранят их элементы на отдельных узлах.  Все узлы для определенного типа контейнера одного размера, поэтому гибкость общецелевого диспетчера памяти не требуется.  Поскольку размер каждого блока памяти известен во время компиляции, диспетчер памяти может быть гораздо проще и быстрее.  
  
 При использовании с контейнерами, не после внесения зависимости \(например, стандартное std::deque std::vector контейнеров библиотеки C\+\+, std::basic\_string\), шаблоны alllocator будут работать правильно, но не могут для предоставления любое улучшение производительности по сравнению с распределителем по умолчанию.  
  
 Распределитель класса шаблона, который описывает объект, который управляет выделение и освобождение памяти для объектов и массивов объектов разрешенного типа.  Объекты распределителя используются несколькими шаблонных классов контейнера в стандартной библиотеке C\+\+.  
  
 Распределителей все шаблоны данного типа:  
  
 `template<class`  `Type` `>`  
  
 `class allocator;`  
  
 , где аргумент `Type` шаблона тип является управляемым экземпляром распределителя.  Стандартная библиотека C\+\+ C предоставляет распределитель по умолчанию, шаблонный класс [allocator](../standard-library/allocator-class.md), который содержится в разделе [\<memory\>](../standard-library/memory.md).  \<allocators\> Заголовок предоставляет следующие распределителей:  
  
-   [allocator\_newdel](../standard-library/allocator-newdel-class.md)  
  
-   [allocator\_unbounded](../standard-library/allocator-unbounded-class.md)  
  
-   [allocator\_fixed\_size](../standard-library/allocator-fixed-size-class.md)  
  
-   [allocator\_variable\_size](../standard-library/allocator-variable-size-class.md)  
  
-   [allocator\_suballoc](../standard-library/allocator-suballoc-class.md)  
  
-   [allocator\_chunklist](../Topic/allocator_chunklist%20Class.md)  
  
 Используйте подходящее создание распределителя в качестве второго аргумента типа создание контейнера, например, в следующем примере кода.  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;`  
  
 \_List0 выделяет узлы с `allocator_chunklist` и фильтром синхронизации по умолчанию.  
  
 Следует использовать макрос [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) для создания шаблонов распределителя с фильтрами синхронизации, отличный от принятого по умолчанию:  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);`  
  
 `std::list<int, alloc<int> > _List1;`  
  
 \_Lst1 выделяет узлы с `allocator_chunklist` и фильтром синхронизации [synchronization\_per\_thread](../standard-library/sync-per-thread-class.md).  
  
 Распределитель блока кэш или фильтр.  Кэш класса шаблона, который принимает один аргумент std::size\_t типа.  Он определяет распределитель блока, выделение и отменить блоки памяти одного размера.  Он должен получить память с помощью оператора `new`, но для этого не требуется выполнять отдельно к оператору `new` для каждого блока.  Он может, например, дополнительного выделения памяти большего блока или отмененных распределение кэшем блоков для дальнейшего распространения.  
  
 С компилятором, не может компилировать rebind значение аргумента std::size\_t, когда был создан экземпляр шаблона не обязательно \_Sz значение аргумента, передаваемого в функциям элемента кэша выделяет и отмены.  
  
 \<allocators\> предоставляет следующие шаблоны кэша:  
  
-   [cache\_freelist](../standard-library/cache-freelist-class.md)  
  
-   [cache\_suballoc](../standard-library/cache-suballoc-class.md)  
  
-   [cache\_chunklist](../standard-library/cache-chunklist-class.md)  
  
 Фильтр распределитель блока, реализующий его функции\-члены с использованием другого блока распределитель, передаваемых в качестве аргумента шаблона.  Наиболее распространенной формой фильтра фильтр синхронизации, который применяет политику синхронизации с доступом элемента управления к функциям элемента экземпляра другого распределителя блока. \<allocators\> предоставляет следующие фильтры синхронизации.  
  
-   [synchronization\_none](../standard-library/sync-none-class.md)  
  
-   [synchronization\_per\_container](../standard-library/sync-per-container-class.md)  
  
-   [synchronization\_per\_thread](../standard-library/sync-per-thread-class.md)  
  
-   [synchronization\_shared](../Topic/sync_shared%20Class.md)  
  
 \<allocators\> также предоставляет фильтр [rts\_alloc](../standard-library/rts-alloc-class.md), который содержит несколько экземпляров распределителя блока и определяет, какой экземпляр, используемый для выделения или освобождение во время выполнения, а не во время компиляции.  Используется с компиляторами, не может компилировать rebind.  
  
 Политика синхронизации определяет, как экземпляр распределителя выполняет одновременных запросов на выделение и освобождение из нескольких потоков.  Самая простая политика передавать все запросы непосредственно через к базовому объекту кэша, и управление синхронизацией пользователю.  Более сложная политика мьютекс может быть использован для сериализации доступ к базовому объекту кэша.  
  
 Если поддержки компилятора при компилировании с одним и продели потоков и многопоточных приложений, то фильтр синхронизации по умолчанию для одного несколькими потоками приложений `sync_none`; во все другие случаи это `sync_shared`.  
  
 Шаблон `cache_freelist` кэша максимальный принимает аргумент класса, максимальное количество элементов, сохраняемых в свободном списке.  
  
 \<allocators\> максимальное количество предоставляет следующие классы:  
  
-   [max\_none](../Topic/max_none%20Class.md)  
  
-   [max\_unbounded](../standard-library/max-unbounded-class.md)  
  
-   [max\_fixed\_size](../standard-library/max-fixed-size-class.md)  
  
-   [max\_variable\_size](../standard-library/max-variable-size-class.md)  
  
### Макросы  
  
|||  
|-|-|  
|[ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)|Создает класс шаблона распределителя.|  
|[CACHE\_CHUNKLIST](../Topic/CACHE_CHUNKLIST%20\(%3Callocators%3E\).md)|Создает `stdext::allocators::cache_chunklist<sizeof(Type)>`.|  
|[CACHE\_FREELIST](../Topic/CACHE_FREELIST%20\(%3Callocators%3E\).md)|Создает `stdext::allocators::cache_freelist<sizeof(Type), max>`.|  
|[CACHE\_SUBALLOC](../Topic/CACHE_SUBALLOC%20\(%3Callocators%3E\).md)|Создает `stdext::allocators::cache_suballoc<sizeof(Type)>`.|  
|[SYNC\_DEFAULT](../Topic/SYNC_DEFAULT%20\(%3Callocators%3E\).md)|Создает фильтр синхронизации.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Callocators%3E\).md)|Проверяет на неравенство между объектами распределителя указанного класса.|  
|[operator\=\=](../Topic/operator==%20\(%3Callocators%3E\).md)|Проверяет на равенство объекты распределителя указанного класса.|  
  
### Классы  
  
|||  
|-|-|  
|[allocator\_base](../standard-library/allocator-base-class.md)|Определяет базовый класс и общие функции, необходимые для создания определенного пользователем распределитель из фильтра синхронизации.|  
|[allocator\_chunklist](../Topic/allocator_chunklist%20Class.md)|Описывает объект, который управляет выделение и освобождение памяти для кэширования типа объектов с помощью [cache\_chunklist](../standard-library/cache-chunklist-class.md).|  
|[allocator\_fixed\_size](../standard-library/allocator-fixed-size-class.md)|Описывает объект, который управляет выделение и освобождение памяти для объектов типа `Type` использование кэша управлянная длина типа [cache\_freelist](../standard-library/cache-freelist-class.md) с [max\_fixed\_size](../standard-library/max-fixed-size-class.md).|  
|[allocator\_newdel](../standard-library/allocator-newdel-class.md)|Реализует распределитель, использующий `operator delete` для отмены блок памяти и `operator new`, чтобы выделить блок памяти.|  
|[allocator\_suballoc](../standard-library/allocator-suballoc-class.md)|Описывает объект, который управляет выделение и освобождение памяти для объектов типа `Type` использование кэша типа [cache\_suballoc](../standard-library/cache-suballoc-class.md).|  
|[allocator\_unbounded](../standard-library/allocator-unbounded-class.md)|Описывает объект, который управляет выделение и освобождение памяти для объектов типа `Type` использование кэша управлянная длина типа [cache\_freelist](../standard-library/cache-freelist-class.md) с [max\_unbounded](../standard-library/max-unbounded-class.md).|  
|[allocator\_variable\_size](../standard-library/allocator-variable-size-class.md)|Описывает объект, который управляет выделение и освобождение памяти для объектов типа `Type` использование кэша управлянная длина типа [cache\_freelist](../standard-library/cache-freelist-class.md) с [max\_variable\_size](../standard-library/max-variable-size-class.md).|  
|[cache\_chunklist](../standard-library/cache-chunklist-class.md)|Определяет распределитель блока, выделение и отменить блоки памяти одного размера.|  
|[cache\_freelist](../standard-library/cache-freelist-class.md)|Определяет распределитель блока, выделение и отменить блоки памяти одного размера.|  
|[cache\_suballoc](../standard-library/cache-suballoc-class.md)|Определяет распределитель блока, выделение и отменить блоки памяти одного размера.|  
|[freelist](../Topic/freelist%20Class.md)|Управляет списком блоков памяти.|  
|[max\_fixed\_size](../standard-library/max-fixed-size-class.md)|Описывает максимальный объект класса, ограничения объект [freelist](../Topic/freelist%20Class.md) в фиксированной максимальной длины.|  
|[max\_none](../Topic/max_none%20Class.md)|Описывает максимальный объект класса, ограничения объект [freelist](../Topic/freelist%20Class.md) в максимальная длина ноль.|  
|[max\_unbounded](../standard-library/max-unbounded-class.md)|Описывает максимальный объект класса, не ограничивает максимальную длину объекта [freelist](../Topic/freelist%20Class.md).|  
|[max\_variable\_size](../standard-library/max-variable-size-class.md)|Описывает максимальный объект класса, ограничения объект [freelist](../Topic/freelist%20Class.md) с максимальной длины, быть пропорционально количеству блоков выделения памяти.|  
|[rts\_alloc](../standard-library/rts-alloc-class.md)|Класс шаблона rts\_alloc описание [фильтр](../standard-library/allocators-header.md), который содержит массив экземпляров кэша и определяет, какой экземпляр, используемый для выделения и освобождение во время выполнения, а не во время компиляции.|  
|[synchronization\_none](../standard-library/sync-none-class.md)|Описывает фильтр синхронизации, не предоставляет какой\-либо синхронизации.|  
|[synchronization\_per\_container](../standard-library/sync-per-container-class.md)|Описывает фильтр синхронизации, предоставляет отдельный объект кэша для каждого объекта распределителя.|  
|[synchronization\_per\_thread](../standard-library/sync-per-thread-class.md)|Описывает фильтр синхронизации, предоставляет отдельный объект кэша для каждого потока.|  
|[synchronization\_shared](../Topic/sync_shared%20Class.md)|Описывает фильтр синхронизации, используется мьютекс с доступом элемента управления объект кэша, совместно используемый всеми распределителями.|  
  
## Требования  
 **Заголовок:**\<allocators\>  
  
 **Пространство имен:** stdext  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)