---
title: "&lt;atomic&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<atomic>"
  - "atomic/std::atomic_int_least32_t"
  - "atomic/std::atomic_ullong"
  - "atomic/std::atomic_ptrdiff_t"
  - "atomic/std::atomic_char16_t"
  - "atomic/std::atomic_schar"
  - "atomic/std::atomic_ulong"
  - "atomic/std::atomic_uint_fast32_t"
  - "atomic/std::atomic_uint8_t"
  - "atomic/std::atomic_int32_t"
  - "atomic/std::atomic_uint_fast64_t"
  - "atomic/std::atomic_uint32_t"
  - "atomic/std::atomic_int16_t"
  - "atomic/std::atomic_uintmax_t"
  - "atomic/std::atomic_intmax_t"
  - "atomic/std::atomic_long"
  - "atomic/std::atomic_int"
  - "atomic/std::atomic_uint_least8_t"
  - "atomic/std::atomic_size_t"
  - "atomic/std::atomic_uint_fast16_t"
  - "atomic/std::atomic_wchar_t"
  - "atomic/std::atomic_int_fast64_t"
  - "atomic/std::atomic_uint_fast8_t"
  - "atomic/std::atomic_int_fast8_t"
  - "atomic/std::atomic_intptr_t"
  - "atomic/std::atomic_uint"
  - "atomic/std::atomic_uint16_t"
  - "atomic/std::atomic_char32_t"
  - "atomic/std::atomic_uint64_t"
  - "atomic/std::atomic_ushort"
  - "atomic/std::atomic_int_least16_t"
  - "atomic/std::atomic_char"
  - "atomic/std::atomic_uint_least32_t"
  - "atomic/std::atomic_uintptr_t"
  - "atomic/std::atomic_short"
  - "atomic/std::atomic_llong"
  - "atomic/std::atomic_uint_least16_t"
  - "atomic/std::atomic_int_fast16_t"
  - "atomic/std::atomic_int_least8_t"
  - "atomic/std::atomic_int_least64_t"
  - "atomic/std::atomic_int_fast32_t"
  - "atomic/std::atomic_uchar"
  - "atomic/std::atomic_int8_t"
  - "atomic/std::atomic_int64_t"
  - "atomic/std::atomic_uint_least64_t"
dev_langs: 
  - "C++"
ms.assetid: e79a6b9f-52ff-48da-9554-654c4e1999f6
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;atomic&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет классы и классы шаблонов для использования типы, которые поддерживают создание атомарных операций.  
  
## Синтаксис  
  
```cpp  
#include <atomic>  
```  
  
## Заметки  
  
> [!NOTE]
>  В коде, компилироваться с помощью **\/clr** или **\/clr:pure**, этот заголовок блокируется.  
  
 Атомарная операция имеет 2 ключевых свойств, помогающие использовать несколько потоков для правильной обработки объект без использования мьютекс блокируют.  
  
-   Поскольку атомарная операция нераздельна, вторая атомарная операция на этом объекте из разных потоков может получить состояние объекта только до или после первой атомарной операцией.  
  
-   На основе его аргумент [memory\_order](../Topic/memory_order%20Enum.md), атомарная операция задает порядок требования для видимости эффектов других атомарных операций в том же потоке.  Следовательно, она блокирует оптимизаций, которые нарушают порядок требования.  
  
 В некоторых платформах, может оказаться невозможным эффективно реализовать атомарные операции для некоторых типов без использования `mutex` блокирует.  Атомарный тип *может от блокировку* при отсутствии атомарные операции с этими использовании типа не блокируют.  
  
 Класс [atomic\_flag](../Topic/atomic_flag%20Structure.md) предоставляет минимальный атомарный тип, который содержит флажок `bool`.  Его операции всегда свободно от блокировку.  
  
 Класс шаблона `atomic<Ty>` сохраняет объект его типа `Ty` аргумента и предоставляет атомарный доступ со сведениями, хранящимися значение.  Можно создать его с помощью любого типа, который может быть скопирован с помощью [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) и выполняется на равенство, используя [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md).  В частности, его можно использовать с пользовательскими типами, которые удовлетворяют этим требованиям, и во многих случаях с плавающей запятой.  
  
 Шаблон также содержит набор специализаций для целочисленных типов и частично специализацию для указателей.  Эти специализации предоставляют дополнительные операции, которые не доступны через первичного шаблона.  
  
## Специализации указателя  
 Специализации `atomic<Ty *>` частично применяются ко всем типам указателей.  Они предоставляют методы для арифметики указателей.  
  
## Целочисленные специализации  
 Специализации `atomic<integral>` применяются ко всем целочисленным типам.  Они предоставляют дополнительные операции, которые не доступны через первичного шаблона.  
  
 Каждый тип `atomic<integral>` имеет соответствующего макроса, который можно использовать в `if directive` определить во время компиляции ли операции для данного типа свободно от блокировку.  Если значение макроса равно нулю, то операции типа не свободно от блокировку.  Если значение равно 1, то операции могут быть свободно от блокировку и проверка среды выполнения не требуется.  Если значение равно 2, то операции свободно от блокировку.  Можно использовать функцию `atomic_is_lock_free` определить ли во время выполнения операции в типе свободно от блокировку.  
  
 Для каждого из целочисленных типов с именем, соответствующим атомарный тип, управляющий объект, целочисленного типа.  Каждый тип `atomic_integral` имеет тот же набор функций\-членов, совпадающие с именами соответствующих создание `atomic<Ty>` и может быть передан в любых функций, не являющихся членами атомарным.  
  
|Тип `atomic_integral`|Целочисленный тип|макрос `atomic_is_lock_free`|  
|---------------------------|-----------------------|----------------------------------|  
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
  
 Имена typedef существуют для специализаций атомарного шаблона для некоторых типов, определенных в заголовке \<inttypes.h\>.  
  
|Атомарный тип|Имя typedef|  
|-------------------|-----------------|  
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
  
## структурам;  
  
|Name|Описание|  
|----------|--------------|  
|[Структура atomic](../standard-library/atomic-structure.md)|Описывает объект, выполняющий атомарных операций на сохраненный значение.|  
|[Структура atomic\_flag](../Topic/atomic_flag%20Structure.md)|Описание объекта, неделимым блоком, наборы и очищает флажок `bool`.|  
  
## перечислениям;  
  
|Name|Описание|  
|----------|--------------|  
|[Перечисление memory\_order](../Topic/memory_order%20Enum.md)|Символические имена, для операций синхронизации на расположения в памяти.  Эти операции влияют на порядок назначения в одном потоке становятся видимыми в других.|  
  
## Функции  
 В следующем списке, функции, которые не заканчивается `_explicit` обладают семантикой соответствующий `_explicit`, за исключением того, что они имеют неявные аргументы [memory\_order](../Topic/memory_order%20Enum.md)`memory_order_seq_cst`.  
  
|Name|Описание|  
|----------|--------------|  
|[Функция atomic\_compare\_exchange\_strong](../Topic/atomic_compare_exchange_strong%20Function.md)|Выполняет операцию *атомарный сравнивать и обмена*.|  
|[Функция atomic\_compare\_exchange\_strong\_explicit](../Topic/atomic_compare_exchange_strong_explicit%20Function.md)|Выполняет операцию *атомарный сравнивать и обмена*.|  
|[Функция atomic\_compare\_exchange\_weak](../Topic/atomic_compare_exchange_weak%20Function.md)|Выполняет операцию *слабое атомарное сравнивает и обмена*.|  
|[Функция atomic\_compare\_exchange\_weak\_explicit](../Topic/atomic_compare_exchange_weak_explicit%20Function.md)|Выполняет операцию *слабое атомарное сравнивает и обмена*.|  
|[Функция atomic\_exchange](../Topic/atomic_exchange%20Function.md)|Заменяет сохраненного значения.|  
|[Функция atomic\_exchange\_explicit](../Topic/atomic_exchange_explicit%20Function.md)|Заменяет сохраненного значения.|  
|[Функция atomic\_fetch\_add](../Topic/atomic_fetch_add%20Function.md)|Добавляет указанное значение в существующих сохраненного значения.|  
|[Функция atomic\_fetch\_add\_explicit](../Topic/atomic_fetch_add_explicit%20Function.md)|Добавляет указанное значение в существующих сохраненного значения.|  
|[Функция atomic\_fetch\_and](../Topic/atomic_fetch_and%20Function.md)|Выполняет операцию побитового `and` на указанном и существующие значения, сохраненные значения.|  
|[Функция atomic\_fetch\_and\_explicit](../Topic/atomic_fetch_and_explicit%20Function.md)|Выполняет операцию побитового `and` на указанном и существующие значения, сохраненные значения.|  
|[Функция atomic\_fetch\_or](../Topic/atomic_fetch_or%20Function.md)|Выполняет операцию побитового `or` на указанном и существующие значения, сохраненные значения.|  
|[Функция atomic\_fetch\_or\_explicit](../Topic/atomic_fetch_or_explicit%20Function.md)|Выполняет операцию побитового `or` на указанном и существующие значения, сохраненные значения.|  
|[Функция atomic\_fetch\_sub](../Topic/atomic_fetch_sub%20Function.md)|Вычитает указанное значение из существующих сохраненного значения.|  
|[Функция atomic\_fetch\_sub\_explicit](../Topic/atomic_fetch_sub_explicit%20Function.md)|Вычитает указанное значение из существующих сохраненного значения.|  
|[Функция atomic\_fetch\_xor](../Topic/atomic_fetch_xor%20Function.md)|Выполняет операцию побитового `exclusive or` на указанном и существующие значения, сохраненные значения.|  
|[Функция atomic\_fetch\_xor\_explicit](../Topic/atomic_fetch_xor_explicit%20Function.md)|Выполняет операцию побитового `exclusive or` на указанном и существующие значения, сохраненные значения.|  
|[Функция atomic\_flag\_clear](../Topic/atomic_flag_clear%20Function.md)|Задает флажок в объекте `atomic_flag` в `false`.|  
|[Функция atomic\_flag\_clear\_explicit](../Topic/atomic_flag_clear_explicit%20Function.md)|Задает флажок в объекте `atomic_flag` в `false`.|  
|[Функция atomic\_flag\_test\_and\_set](../Topic/atomic_flag_test_and_set%20Function.md)|Задает флажок в объекте `atomic_flag` в `true`.|  
|[Функция atomic\_flag\_test\_and\_set\_explicit](../Topic/atomic_flag_test_and_set_explicit%20Function.md)|Задает флажок в объекте `atomic_flag` в `true`.|  
|[Функция atomic\_init](../Topic/atomic_init%20Function.md)|Задает значения, хранящиеся в объекте `atomic`.|  
|[atomic\_is\_lock\_free \- функция](../Topic/atomic_is_lock_free%20Function.md)|Определяет, является ли атомарных операций в указанном объекте свободно от блокировку.|  
|[Функция atomic\_load](../Topic/atomic_load%20Function.md)|Неделимым блоком, извлекает значение.|  
|[Функция atomic\_load\_explicit](../Topic/atomic_load_explicit%20Function.md)|Неделимым блоком, извлекает значение.|  
|[Функция atomic\_signal\_fence](../Topic/atomic_signal_fence%20Function.md)|Действует как *загородка*, задает требования к памяти порядок обнести вызывающий поток с выполнены сигнала обработчики в том же потоке.|  
|[Функция atomic\_store](../Topic/atomic_store%20Function.md)|Неделимым блоком, сохраняет значение.|  
|[Функция atomic\_store\_explicit](../Topic/atomic_store_explicit%20Function.md)|Неделимым блоком, сохраняет значение.|  
|[Функция atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md)|Действует как *загородка*, задает требования к памяти при упорядочивании по отношению к другим загородкам.|  
|[Функция kill\_dependency](../Topic/kill_dependency%20Function.md)|Прерывает возможную цепочка зависимостей.|  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)