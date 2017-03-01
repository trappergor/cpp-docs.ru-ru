---
title: "&lt;atomic&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <atomic>
- atomic/std::atomic_int_least32_t
- atomic/std::atomic_ullong
- atomic/std::atomic_ptrdiff_t
- atomic/std::atomic_char16_t
- atomic/std::atomic_schar
- atomic/std::atomic_ulong
- atomic/std::atomic_uint_fast32_t
- atomic/std::atomic_uint8_t
- atomic/std::atomic_int32_t
- atomic/std::atomic_uint_fast64_t
- atomic/std::atomic_uint32_t
- atomic/std::atomic_int16_t
- atomic/std::atomic_uintmax_t
- atomic/std::atomic_intmax_t
- atomic/std::atomic_long
- atomic/std::atomic_int
- atomic/std::atomic_uint_least8_t
- atomic/std::atomic_size_t
- atomic/std::atomic_uint_fast16_t
- atomic/std::atomic_wchar_t
- atomic/std::atomic_int_fast64_t
- atomic/std::atomic_uint_fast8_t
- atomic/std::atomic_int_fast8_t
- atomic/std::atomic_intptr_t
- atomic/std::atomic_uint
- atomic/std::atomic_uint16_t
- atomic/std::atomic_char32_t
- atomic/std::atomic_uint64_t
- atomic/std::atomic_ushort
- atomic/std::atomic_int_least16_t
- atomic/std::atomic_char
- atomic/std::atomic_uint_least32_t
- atomic/std::atomic_uintptr_t
- atomic/std::atomic_short
- atomic/std::atomic_llong
- atomic/std::atomic_uint_least16_t
- atomic/std::atomic_int_fast16_t
- atomic/std::atomic_int_least8_t
- atomic/std::atomic_int_least64_t
- atomic/std::atomic_int_fast32_t
- atomic/std::atomic_uchar
- atomic/std::atomic_int8_t
- atomic/std::atomic_int64_t
- atomic/std::atomic_uint_least64_t
dev_langs:
- C++
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 8346982360dbc6ecfaae296e48da9464b91190b4
ms.lasthandoff: 02/24/2017

---
# <a name="ltatomicgt"></a>&lt;atomic&gt;
Определяет классы и классы шаблонов для создания типов, поддерживающих атомарные операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <atomic>  
```  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В коде, который компилируется с помощью **/CLR**, этот заголовок будет заблокирован.  
  
 Атомарная операция имеет&2; ключевых свойства, позволяющих организовать безопасный доступ к объекту из нескольких потоков без использования мьютексов.  
  
-   Поскольку атомарная операция нераздельна, вторая атомарная операция, вызванная для заданного объекта из другого потока, может получить состояние объекта только до или после первой атомарной операции.  
  
-   На основе своего аргумента [memory_order](../standard-library/atomic-enums.md#memory_order_enum) атомарная операция устанавливает требования упорядоченности для видимости влияния других атомарных операций в том же потоке. Следовательно, она подавляет оптимизации компилятора, которые нарушают требования к упорядоченности.  
  
 На некоторых платформах бывает невозможно эффективно реализовать атомарные операции для некоторых типов без использования блокировок `mutex`. Атомарный тип является *неблокирующим*, если никакие атомарные операции с этим типом не используют блокировки.  
  
 **C ++&11;**: в обработчиках сигналов можно выполнять атомарные операции с объектом `obj`, если `obj.is_lock_free()` или `atomic_is_lock_free(x)` имеет значение true.  
  
 Класс [atomic_flag](../standard-library/atomic-flag-structure.md) предоставляет минимальный атомарный тип, который содержит флаг `bool`. Его операции всегда являются неблокирующими.  
  
 Класс шаблона `atomic<T>` хранит объект типа его аргумента `T` и предоставляет атомарный доступ к этому сохраненному значению. Его можно создать с помощью любого типа, который может быть скопирован с помощью [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) и проверен на равенство с помощью [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md). В частности, его можно использовать с пользовательскими типами, которые соответствуют этим требованиям, и во многих случаях с типами с плавающей запятой.  
  
 Шаблон также имеет ряд специализаций для целочисленных типов и частичную специализацию для указателей. Эти специализации предоставляют дополнительные операции, которые недоступны из первичного шаблона.  
  
## <a name="pointer-specializations"></a>Специализации для указателей  
 Частичные специализации `atomic<T *>` применяются для всех типов указателей. Они предоставляют методы для расчетов с указателями.  
  
## <a name="integral-specializations"></a>Специализации для целочисленных типов  
 Специализации `atomic<integral>` применяются для всех целочисленных типов. Они предоставляют дополнительные операции, которые недоступны из первичного шаблона.  
  
 Каждый тип `atomic<integral>` имеет соответствующий макрос, который можно использовать в `if directive` для определения во время компиляции, являются ли операции этого типа неблокирующими. Если значение макроса равно нулю, операции типа не являются неблокирующими. Если значение равно 1, операции могут быть неблокирующими, и требуется проверка времени выполнения. Если значение равно 2, операции являются неблокирующими. Вы можете использовать функцию `atomic_is_lock_free` для определения во время выполнения, являются ли операции с типом неблокирующими.  
  
 Для каждого из целочисленных типов существует соответствующий именованный атомарный тип, который управляет объектом целочисленного типа. Каждый тип `atomic_integral` имеет тот же набор функций-членов, что и соответствующий экземпляр `atomic<T>`, и может быть передан в любую из атомарных функций, не являющихся членами.  
  
|Тип `atomic_integral`|Целочисленный тип|Макрос `atomic_is_lock_free`|  
|----------------------------|-------------------|---------------------------------|  
|`atomic_char`|`char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_schar`|`signed char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_uchar`|`unsigned char`|`ATOMIC_CHAR_LOCK_FREE`|  
|`atomic_char16_t`|`char16_t`|`ATOMIC_CHAR16_T_LOCK_FREE`|  
|`atomic_char32_t`|`char32_t`|`ATOMIC_CHAR32_T_LOCK_FREE`|  
|`atomic_wchar_t`|`wchar_t`|`ATOMIC_WCHAR_T_LOCK_FREE`|  
|`atomic_short`|`short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_ushort`|`unsigned short`|`ATOMIC_SHORT_LOCK_FREE`|  
|`atomic_int`|`int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_uint`|`unsigned int`|`ATOMIC_INT_LOCK_FREE`|  
|`atomic_long`|`long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_ulong`|`unsigned long`|`ATOMIC_LONG_LOCK_FREE`|  
|`atomic_llong`|`long long`|`ATOMIC_LLONG_LOCK_FREE`|  
|`atomic_ullong`|`unsigned long long`|`ATOMIC_LLONG_LOCK_FREE`|  
  
 Имена typedef существуют для специализаций атомарного шаблона для некоторых типов, определенных в заголовке \<inttypes.h>.  
  
|Атомарный тип|Имя typedef|  
|-----------------|------------------|  
|`atomic_int8_t`|`atomic<int8_t>`|  
|`atomic_uint8_t`|`atomic<uint8_t>`|  
|`atomic_int16_t`|`atomic<int16_t>`|  
|`atomic_uint16_t`|`atomic<uint16_t>`|  
|`atomic_int32_t`|`atomic<int32_t>`|  
|`atomic_uint32_t`|`atomic<uint32_t>`|  
|`atomic_int64_t`|`atomic<int64_t>`|  
|`atomic_uint64_t`|`atomic<uint64_t>`|  
|`atomic_int_least8_t`|`atomic<int_least8_t>`|  
|`atomic_uint_least8_t`|`atomic<uint_least8_t>`|  
|`atomic_int_least16_t`|`atomic<int_least16_t>`|  
|`atomic_uint_least16_t`|`atomic<uint_least16_t>`|  
|`atomic_int_least32_t`|`atomic<int_least32_t>`|  
|`atomic_uint_least32_t`|`atomic<uint_least32_t>`|  
|`atomic_int_least64_t`|`atomic<int_least64_t>`|  
|`atomic_uint_least64_t`|`atomic<uint_least64_t>`|  
|`atomic_int_fast8_t`|`atomic<int_fast8_t>`|  
|`atomic_uint_fast8_t`|`atomic<uint_fast8_t>`|  
|`atomic_int_fast16_t`|`atomic<int_fast16_t>`|  
|`atomic_uint_fast16_`|`atomic<uint_fast16_t>`|  
|`atomic_int_fast32_t`|`atomic<int_fast32_t>`|  
|`atomic_uint_fast32_t`|`atomic<uint_fast32_t>`|  
|`atomic_int_fast64_t`|`atomic<int_fast64_t>`|  
|`atomic_uint_fast64_t`|`atomic<uint_fast64_t>`|  
|`atomic_intptr_t`|`atomic<intptr_t>`|  
|`atomic_uintptr_t`|`atomic<uintptr_t>`|  
|`atomic_size_t`|`atomic<size_t>`|  
|`atomic_ptrdiff_t`|`atomic<ptrdiff_t>`|  
|`atomic_intmax_t`|`atomic<intmax_t>`|  
|`atomic_uintmax_t`|`atomic<uintmax_t>`|  
  
## <a name="structs"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура atomic](../standard-library/atomic-structure.md)|Описывает объект, который выполняет атомарные операции с сохраненным значением.|  
|[Структура atomic_flag](../standard-library/atomic-flag-structure.md)|Описывает объект, который автоматически устанавливает и очищает флаг `bool`.|  
  
## <a name="enums"></a>перечислениям;  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление memory_order](../standard-library/atomic-enums.md#memory_order_enum)|Предоставляет символьные имена для операций синхронизации в областях памяти. Эти операции влияют на то, как присвоения в одном потоке становятся видимыми в другом.|  
  
## <a name="functions"></a>Функции  
 В следующем списке функции, которые не заканчиваются на `_explicit`, имеют семантику соответствующего `_explicit`, за исключением того, что они имеют неявные аргументы [memory_order](../standard-library/atomic-enums.md#memory_order_enum) `memory_order_seq_cst`.  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция atomic_compare_exchange_strong](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_function)|Выполняет *атомарную операцию сравнения и обмена*.|  
|[Функция atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit_function)|Выполняет *атомарную операцию сравнения и обмена*.|  
|[Функция atomic_compare_exchange_weak](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_function)|Выполняет *слабую атомарную операцию сравнения и обмена*.|  
|[Функция atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit_function)|Выполняет *слабую атомарную операцию сравнения и обмена*.|  
|[Функция atomic_exchange](../standard-library/atomic-functions.md#atomic_exchange_function)|Заменяет сохраненное значение.|  
|[Функция atomic_exchange_explicit](../standard-library/atomic-functions.md#atomic_exchange_explicit_function)|Заменяет сохраненное значение.|  
|[Функция atomic_fetch_add](../standard-library/atomic-functions.md#atomic_fetch_add_function)|Добавляет указанное значение к существующему хранимому значению.|  
|[Функция atomic_fetch_add_explicit](../standard-library/atomic-functions.md#atomic_fetch_add_explicit_function)|Добавляет указанное значение к существующему хранимому значению.|  
|[Функция atomic_fetch_and](../standard-library/atomic-functions.md#atomic_fetch_and_function)|Выполняет побитовую операцию `and` с указанным значением и существующим хранимым значением.|  
|[Функция atomic_fetch_and_explicit](../standard-library/atomic-functions.md#atomic_fetch_and_explicit_function)|Выполняет побитовую операцию `and` с указанным значением и существующим хранимым значением.|  
|[Функция atomic_fetch_or](../standard-library/atomic-functions.md#atomic_fetch_or_function)|Выполняет побитовую операцию `or` с указанным значением и существующим хранимым значением.|  
|[Функция atomic_fetch_or_explicit](../standard-library/atomic-functions.md#atomic_fetch_or_explicit_function)|Выполняет побитовую операцию `or` с указанным значением и существующим хранимым значением.|  
|[Функция atomic_fetch_sub](../standard-library/atomic-functions.md#atomic_fetch_sub_function)|Вычитает указанное значение из существующего хранимого значения.|  
|[Функция atomic_fetch_sub_explicit](../standard-library/atomic-functions.md#atomic_fetch_sub_explicit_function)|Вычитает указанное значение из существующего хранимого значения.|  
|[Функция atomic_fetch_xor](../standard-library/atomic-functions.md#atomic_fetch_xor_function)|Выполняет побитовую операцию `exclusive or` с указанным значением и существующим хранимым значением.|  
|[Функция atomic_fetch_xor_explicit](../standard-library/atomic-functions.md#atomic_fetch_xor_explicit_function)|Выполняет побитовую операцию `exclusive or` с указанным значением и существующим хранимым значением.|  
|[Функция atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear_function)|Устанавливает флаг в объекте `atomic_flag` в значение `false`.|  
|[Функция atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit_function)|Устанавливает флаг в объекте `atomic_flag` в значение `false`.|  
|[Функция atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set_function)|Устанавливает флаг в объекте `atomic_flag` в значение `true`.|  
|[Функция atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit_function)|Устанавливает флаг в объекте `atomic_flag` в значение `true`.|  
|[Функция atomic_init](../standard-library/atomic-functions.md#atomic_init_function)|Задает сохраненное значение в объекте `atomic`.|  
|[Функция atomic_is_lock_free](../standard-library/atomic-functions.md#atomic_is_lock_free_function)|Указывает, являются ли атомарные операции с указанным объектом неблокирующими.|  
|[Функция atomic_load](../standard-library/atomic-functions.md#atomic_load_function)|Атомарным образом получает значение.|  
|[Функция atomic_load_explicit](../standard-library/atomic-functions.md#atomic_load_explicit_function)|Атомарным образом получает значение.|  
|[Функция atomic_signal_fence](../standard-library/atomic-functions.md#atomic_signal_fence_function)|Действует как *граница*, устанавливающая требования упорядочивания памяти между границами в вызывающем потоке, который имеет обработчики сигнала, выполняющиеся в том же потоке.|  
|[Функция atomic_store](../standard-library/atomic-functions.md#atomic_store_function)|Атомарным образом сохраняет значение.|  
|[Функция atomic_store_explicit](../standard-library/atomic-functions.md#atomic_store_explicit_function)|Атомарным образом сохраняет значение.|  
|[Функция atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence_function)|Действует как *граница*, которая устанавливает требования упорядочивания относительно других границ.|  
|[Функция kill_dependency](../standard-library/atomic-functions.md#kill_dependency_function)|Разрывает возможную цепочку зависимостей.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)






