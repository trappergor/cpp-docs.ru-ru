---
title: "&lt;Распределители&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <allocators>
dev_langs:
- C++
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 386069d436c004dec19cd6edc7f5689971331227
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltallocatorsgt"></a>&lt;Распределители&gt;
Определяются несколько шаблонов, упрощающих выделение и освобождение блоков памяти для контейнеров на основе узлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <allocators>  
```  
  
## <a name="remarks"></a>Примечания  
 Заголовок \<allocators> предоставляет шесть шаблонов распределителя, которые могут использоваться для выбора стратегии управления памятью для контейнеров на основе узлов. Для использования с этими шаблонами он также предоставляет несколько разных фильтров синхронизации, позволяющих настроить стратегию управления памятью во множестве разных многопоточных схем (включая отсутствие). Сопоставление стратегии управления памятью с известными шаблонами использования памяти и требованиями к синхронизации конкретного приложения часто может повысить скорость или уменьшить требования к общей памяти приложения.  
  
 Шаблоны распределителя реализуются с многократно используемыми компонентами, которые можно настраивать или заменять, чтобы обеспечить дополнительные стратегии управления памятью.  
  
 Контейнеры на основе узла в стандартной библиотеке C++ (std::list, std::set, std::multiset, std::map и std::multimap) хранят свои элементы в отдельных узлах. Все узлы для конкретного типа контейнера имеют одинаковый размер, поэтому не требуется гибкость диспетчера памяти общего назначения. Так как размер каждого блока памяти становится известен во время компиляции, диспетчер памяти может быть гораздо проще и быстрее.  
  
 При использовании с контейнерами, которые не основаны на узлах (такими как контейнеры std::vector, std::deque и std::basic_string стандартной библиотеки C++), шаблоны распределителя будут работать правильно, но скорее всего не обеспечат повышение производительности на основе распределителя по умолчанию.  
  
 Allocator — это класс шаблона, описывающий объект, который управляет выделением и освобождением памяти для объектов и массивов объектов шаблона, а также объект, который управляет выделением и освобождением памяти для массивов объектов указанного типа. Объекты распределителя используются несколькими классами шаблонов контейнера из стандартной библиотеки C++.  
  
 Распределители представляют собой шаблоны типа  
  
 `template<class` `Type` `>`  
  
 `class allocator;`  
  
 где аргумент шаблона `Type` — это тип, управляемый экземпляром распределителя. Стандартная библиотека C++ предоставляет распределитель по умолчанию, [allocator](../standard-library/allocator-class.md) класса шаблона, который задается в [ \<memory>](../standard-library/memory.md). Заголовок \<allocators> предоставляет следующие распределители:  
  
- [allocator_newdel](../standard-library/allocator-newdel-class.md)  
  
- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)  
  
- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)  
  
- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)  
  
- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)  
  
- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)  
  
 При создании контейнера используйте соответствующий экземпляр распределителя как второй аргумент типа, как показано в следующем примере кода.  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;`  
  
 _List0 выделяет узлы с `allocator_chunklist` и фильтром синхронизации по умолчанию.  
  
 Используйте макрос [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) для создания шаблонов распределителя с фильтрами синхронизации, отличными от установленных по умолчанию:  
  
 `#include <list>`  
  
 `#include <allocators>`  
  
 `ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);`  
  
 `std::list<int, alloc<int> > _List1;`  
  
 _Lst1 выделяет узлы с `allocator_chunklist` и фильтр синхронизации [sync_per_thread](../standard-library/sync-per-thread-class.md).  
  
 Распределитель блоков — это кэш или фильтр. Кэш — это класс шаблона, принимающий один аргумент типа std::size_t. Он определяет распределитель блоков, который выделяет и освобождает блоки памяти одного размера. Он должен получать память с помощью оператора `new`, но отдельный вызов оператора `new` для каждого блока выполнять не требуется. Он может, например, дополнительно выделить память из блока большего размера или кэша освобожденных блоков для последующего перераспределения.  
  
 С компилятором, которому не удается скомпилировать повторную привязку значения аргумента std::size_t, использовавшегося при создании экземпляра шаблона, необязательно передавать значение аргумента _Sz в функции-члены кэша для выделения и освобождения.  
  
 \<allocators> предоставляет следующие шаблоны кэша:  
  
- [cache_freelist](../standard-library/cache-freelist-class.md)  
  
- [cache_suballoc](../standard-library/cache-suballoc-class.md)  
  
- [cache_chunklist](../standard-library/cache-chunklist-class.md)  
  
 Фильтр — это распределитель блоков, который реализует свои функции-члены с помощью другого распределителя блоков, который передается в него как аргумент шаблона. Наиболее распространенная форма фильтра — это фильтр синхронизации, который применяет политику синхронизации для управления доступом к функциям-членам экземпляра другого распределителя блоков. \<allocators> предоставляет следующие фильтры синхронизации:  
  
- [sync_none](../standard-library/sync-none-class.md)  
  
- [sync_per_container](../standard-library/sync-per-container-class.md)  
  
- [sync_per_thread](../standard-library/sync-per-thread-class.md)  
  
- [sync_shared](../standard-library/sync-shared-class.md)  
  
 \<allocators> также предоставляет фильтр [rts_alloc](../standard-library/rts-alloc-class.md), который содержит несколько экземпляров распределителей блоков и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.  
  
 Политика синхронизации определяет, как экземпляр распределителя обрабатывает одновременные запросы на выделение и освобождение из нескольких потоков. Самая простая политика заключается в том, что все запросы передаются напрямую в базовый объект кэша, оставляя управление синхронизацией пользователю. Более сложная политика может заключаться в использовании мьютекса для сериализации доступа к базовому объекту кэша.  
  
 Если компилятор поддерживает компиляцию как однопоточных, так и многопоточных приложений, фильтр синхронизации по умолчанию для однопоточных приложений — `sync_none`; для всех остальных случаев — это `sync_shared`.  
  
 Шаблон кэша `cache_freelist` принимает аргумент класса max, который определяет максимальное число элементов для хранения в списке свободных элементов.  
  
 \<allocators> предоставляет следующие классы max:  
  
- [max_none](../standard-library/max-none-class.md)  
  
- [max_unbounded](../standard-library/max-unbounded-class.md)  
  
- [max_fixed_size](../standard-library/max-fixed-size-class.md)  
  
- [max_variable_size](../standard-library/max-variable-size-class.md)  
  
### <a name="macros"></a>Макросы  
  
|||  
|-|-|  
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|Создает класс шаблона распределителя.|  
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|Создает `stdext::allocators::cache_chunklist<sizeof(Type)>`.|  
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|Создает `stdext::allocators::cache_freelist<sizeof(Type), max>`.|  
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|Создает `stdext::allocators::cache_suballoc<sizeof(Type)>`.|  
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|Создает фильтр синхронизации.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[operator!= (\<allocators>)](../standard-library/allocators-operators.md#op_neq)|Проверяет на неравенство между объектами распределителя указанного класса.|  
|[operator== (\<allocators>)](../standard-library/allocators-operators.md#op_eq_eq)|Проверяет на равенство объекты распределителя указанного класса.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[allocator_base](../standard-library/allocator-base-class.md)|Определяет базовый класс и общие функции, необходимые для создания определяемого пользователем распределителя из фильтра синхронизации.|  
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов, использующих кэш типа [cache_chunklist](../standard-library/cache-chunklist-class.md).|  
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_fixed_size](../standard-library/max-fixed-size-class.md).|  
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|Реализует распределителя, который использует `operator delete` для освобождения блока памяти и `operator new` для выделения блока памяти.|  
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_suballoc](../standard-library/cache-suballoc-class.md).|  
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_unbounded](../standard-library/max-unbounded-class.md).|  
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_variable_size](../standard-library/max-variable-size-class.md).|  
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|Задает распределитель блоков, который выделяет и освобождает блоки памяти одного размера.|  
|[cache_freelist](../standard-library/cache-freelist-class.md)|Задает распределитель блоков, который выделяет и освобождает блоки памяти одного размера.|  
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|Задает распределитель блоков, который выделяет и освобождает блоки памяти одного размера.|  
|[freelist](../standard-library/freelist-class.md)|Управляет списком блоков памяти.|  
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|Описывает объект класса max, который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) определенным значением.|  
|[max_none](../standard-library/max-none-class.md)|Описывает объект класса max, который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.|  
|[max_unbounded](../standard-library/max-unbounded-class.md)|Описывает объект класса max, который не ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md).|  
|[max_variable_size](../standard-library/max-variable-size-class.md)|Описывает объект класса max, который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) значением, приблизительно пропорциональным количеству выделенных блоков памяти.|  
|[rts_alloc](../standard-library/rts-alloc-class.md)|Класс шаблона rts_alloc описывает [фильтр](../standard-library/allocators-header.md), содержащий массив экземпляров кэша, и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции.|  
|[sync_none](../standard-library/sync-none-class.md)|Описывает фильтр синхронизации, который не предоставляет синхронизацию.|  
|[sync_per_container](../standard-library/sync-per-container-class.md)|Описывает фильтр синхронизации, предоставляющий отдельный объект кэша для каждого объекта распределителя.|  
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|Описывает фильтр синхронизации, предоставляющий отдельный объект кэша для каждого потока.|  
|[sync_shared](../standard-library/sync-shared-class.md)|Описывает фильтр синхронизации, использующий мьютекс для управления доступом к объекту кэша, который является общим для всех распределителей.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)



