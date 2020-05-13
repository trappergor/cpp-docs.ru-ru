---
title: '&lt;Распределители&gt;'
ms.date: 11/04/2016
f1_keywords:
- <allocators>
helpviewer_keywords:
- allocators header
ms.assetid: 4393a607-4df8-4278-bbb2-c8ec52e60b83
ms.openlocfilehash: f6be154be68cd5e43fd6f934d88c04fb25be9dc5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754442"
---
# <a name="ltallocatorsgt"></a>&lt;Распределители&gt;

Определяются несколько шаблонов, упрощающих выделение и освобождение блоков памяти для контейнеров на основе узлов.

## <a name="syntax"></a>Синтаксис

```cpp
#include <allocators>
```

> [!NOTE]
> \<>- инемента, начиная с версии Visual Studio 2019 версии 16.3.

## <a name="remarks"></a>Remarks

Заголовок \<allocators> предоставляет шесть шаблонов распределителя, которые могут использоваться для выбора стратегии управления памятью для контейнеров на основе узлов. Для использования с этими шаблонами он также предоставляет несколько разных фильтров синхронизации, позволяющих настроить стратегию управления памятью во множестве разных многопоточных схем (включая отсутствие). Можно ускорить приложение или уменьшить его требования к памяти, сопоставив стратегию управления памятью с шаблонами использования памяти и требованиями синхронизации.

Шаблоны распределителя реализуются с многократно используемыми компонентами, которые можно настраивать или заменять, чтобы обеспечить дополнительные стратегии управления памятью.

Контейнеры на основе узлов в Стандартной библиотеке СЗ (std::list, std::set, std::multiset, std::map и std::multimap) хранят свои элементы в отдельных узлах. Все узлы для конкретного типа контейнера имеют одинаковый размер, поэтому не требуется гибкость диспетчера памяти общего назначения. Так как размер каждого блока памяти становится известен во время компиляции, диспетчер памяти может быть гораздо проще и быстрее.

При использовании с контейнерами, которые не основаны на узлах (например, контейнеры стандартной библиотеки СЗ Standard Library std::vector std::deque, и std::basic_string), шаблоны распределителя будут работать правильно, но вряд ли обеспечат какое-либо улучшение производительности по сравнению с распределителем по умолчанию.

Распределительщик — это шаблон класса, описывающий объект, управляющий распределением и высвобождением объектов и массивов объектов определенного типа. Объекты allocator используются несколькими шаблонами контейнерного класса в Стандартной библиотеке СЗ.

Распределители представляют собой шаблоны типа

```cpp
template<class Type>
class allocator;
```

где аргумент шаблона `Type` — это тип, управляемый экземпляром распределителя. Стандартная библиотека СЗ предоставляет разлесть по умолчанию, [разлесть](../standard-library/allocator-class.md)шаблона класса, которая определяется в [ \<памяти>. ](../standard-library/memory.md) Заголовок \<allocators> предоставляет следующие распределители:

- [allocator_newdel](../standard-library/allocator-newdel-class.md)

- [allocator_unbounded](../standard-library/allocator-unbounded-class.md)

- [allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)

- [allocator_variable_size](../standard-library/allocator-variable-size-class.md)

- [allocator_suballoc](../standard-library/allocator-suballoc-class.md)

- [allocator_chunklist](../standard-library/allocator-chunklist-class.md)

При создании контейнера используйте соответствующий экземпляр распределителя как второй аргумент типа, как показано в следующем примере кода.

```cpp
#include <list>
#include <allocators>
std::list<int, stdext::allocators::allocator_chunklist<int> > _List0;
```

_List0 выделяет узлы с `allocator_chunklist` и фильтром синхронизации по умолчанию.

Используйте макрос [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) для создания шаблонов распределителя с фильтрами синхронизации, отличными от установленных по умолчанию:

```cpp
#include <list>
#include <allocators>
ALLOCATOR_DECL(CACHE_CHUNKLIST, stdext::allocators::sync_per_thread, Alloc);
std::list<int, alloc<int> > _List1;
```

_Lst1 выделяет узлы с `allocator_chunklist` и фильтр синхронизации [sync_per_thread](../standard-library/sync-per-thread-class.md).

Распределитель блоков — это кэш или фильтр. Кэш — это шаблон класса, который использует один аргумент типа std::size_t. Он определяет распределитель блоков, который выделяет и освобождает блоки памяти одного размера. Он должен получить память с помощью оператора **новый,** но он не должен делать отдельный вызов **оператору новый** для каждого блока. Он может, например, дополнительно выделить память из блока большего размера или кэша освобожденных блоков для последующего перераспределения.

С компилятором, который не может перезавязать значение std::size_t аргумент, используемый при мгновенном использовании шаблона, не обязательно является значением аргумента, _Sz передается функциям члена кэша, распределять и распределять.

\<allocators> предоставляет следующие шаблоны кэша:

- [cache_freelist](../standard-library/cache-freelist-class.md)

- [cache_suballoc](../standard-library/cache-suballoc-class.md)

- [cache_chunklist](../standard-library/cache-chunklist-class.md)

Фильтр — это разлядатор блока, который реализует свои функции члена с помощью другого разлестья блока, который передается ему в качестве аргумента шаблона. Наиболее распространенная форма фильтра — это фильтр синхронизации, который применяет политику синхронизации для управления доступом к функциям-членам экземпляра другого распределителя блоков. \<allocators> предоставляет следующие фильтры синхронизации:

- [sync_none](../standard-library/sync-none-class.md)

- [sync_per_container](../standard-library/sync-per-container-class.md)

- [sync_per_thread](../standard-library/sync-per-thread-class.md)

- [sync_shared](../standard-library/sync-shared-class.md)

\<allocators> также предоставляет фильтр [rts_alloc](../standard-library/rts-alloc-class.md), который содержит несколько экземпляров распределителей блоков и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.

Политика синхронизации определяет, как экземпляр распределителя обрабатывает одновременные запросы на выделение и освобождение из нескольких потоков. Самая простая политика заключается в том, что все запросы передаются напрямую в базовый объект кэша, оставляя управление синхронизацией пользователю. Более сложная политика может заключаться в использовании мьютекса для сериализации доступа к базовому объекту кэша.

Если компилятор поддерживает компиляцию как однопоточных, так и многопоточных приложений, фильтр синхронизации по умолчанию для однопоточных приложений — `sync_none`; для всех остальных случаев — это `sync_shared`.

Шаблон `cache_freelist` кэша занимает аргумент max class, который определяет максимальное количество элементов, которые будут храниться в свободном списке.

\<allocators> предоставляет следующие классы max:

- [max_none](../standard-library/max-none-class.md)

- [max_unbounded](../standard-library/max-unbounded-class.md)

- [max_fixed_size](../standard-library/max-fixed-size-class.md)

- [max_variable_size](../standard-library/max-variable-size-class.md)

### <a name="macros"></a>Макросы

|Макрос|Описание|
|-|-|
|[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)|Дает шаблон класса разлесть.|
|[CACHE_CHUNKLIST](../standard-library/allocators-functions.md#cache_chunklist)|Создает `stdext::allocators::cache_chunklist<sizeof(Type)>`.|
|[CACHE_FREELIST](../standard-library/allocators-functions.md#cache_freelist)|Создает `stdext::allocators::cache_freelist<sizeof(Type), max>`.|
|[CACHE_SUBALLOC](../standard-library/allocators-functions.md#cache_suballoc)|Создает `stdext::allocators::cache_suballoc<sizeof(Type)>`.|
|[SYNC_DEFAULT](../standard-library/allocators-functions.md#sync_default)|Создает фильтр синхронизации.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор! (\<>-](../standard-library/allocators-operators.md#op_neq)|Проверяет на неравенство между объектами распределителя указанного класса.|
|[operator== (\<allocators>)](../standard-library/allocators-operators.md#op_eq_eq)|Проверяет на равенство объекты распределителя указанного класса.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[allocator_base](../standard-library/allocator-base-class.md)|Определяет базовый класс и общие функции, необходимые для создания определяемого пользователем распределителя из фильтра синхронизации.|
|[allocator_chunklist](../standard-library/allocator-chunklist-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов, использующих кэш типа [cache_chunklist](../standard-library/cache-chunklist-class.md).|
|[allocator_fixed_size](../standard-library/allocator-fixed-size-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_fixed_size](../standard-library/max-fixed-size-class.md).|
|[allocator_newdel](../standard-library/allocator-newdel-class.md)|Реализует распределительщик, который использует **удаление оператора** для дераспределения блока памяти и **нового оператора** для выделения блока памяти.|
|[allocator_suballoc](../standard-library/allocator-suballoc-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_suballoc](../standard-library/cache-suballoc-class.md).|
|[allocator_unbounded](../standard-library/allocator-unbounded-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_unbounded](../standard-library/max-unbounded-class.md).|
|[allocator_variable_size](../standard-library/allocator-variable-size-class.md)|Описывает объект, который управляет выделением и освобождением памяти для объектов типа `Type`, использующих кэш типа [cache_freelist](../standard-library/cache-freelist-class.md) с длиной, управляемой классом [max_variable_size](../standard-library/max-variable-size-class.md).|
|[cache_chunklist](../standard-library/cache-chunklist-class.md)|Задает распределитель блоков, который выделяет и освобождает блоки памяти одного размера.|
|[cache_freelist](../standard-library/cache-freelist-class.md)|Задает распределитель блоков, который выделяет и освобождает блоки памяти одного размера.|
|[cache_suballoc](../standard-library/cache-suballoc-class.md)|Задает распределитель блоков, который выделяет и освобождает блоки памяти одного размера.|
|[freelist](../standard-library/freelist-class.md)|Управляет списком блоков памяти.|
|[max_fixed_size](../standard-library/max-fixed-size-class.md)|Описывает объект max class, который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) определенным значением.|
|[max_none](../standard-library/max-none-class.md)|Описывает объект max class, который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.|
|[max_unbounded](../standard-library/max-unbounded-class.md)|Описывает объект max class, который не ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md).|
|[max_variable_size](../standard-library/max-variable-size-class.md)|Описывает объект max class, который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) до значения, приблизительно пропорционального количеству выделенных блоков памяти.|
|[rts_alloc](../standard-library/rts-alloc-class.md)|Шаблон rts_alloc класса описывает [фильтр,](../standard-library/allocators-header.md) который содержит массив экземпляров кэша, и определяет, какой экземпляр использовать для распределения и распределения во время выполнения, а не во время компиляции.|
|[sync_none](../standard-library/sync-none-class.md)|Описывает фильтр синхронизации, который не предоставляет синхронизацию.|
|[sync_per_container](../standard-library/sync-per-container-class.md)|Описывает фильтр синхронизации, предоставляющий отдельный объект кэша для каждого объекта распределителя.|
|[sync_per_thread](../standard-library/sync-per-thread-class.md)|Описывает фильтр синхронизации, предоставляющий отдельный объект кэша для каждого потока.|
|[sync_shared](../standard-library/sync-shared-class.md)|Описывает фильтр синхронизации, использующий мьютекс для управления доступом к объекту кэша, который является общим для всех распределителей.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)
