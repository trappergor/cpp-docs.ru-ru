---
title: "Пространство имен Concurrency (C++ AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: a62955c94771320a64027f4f820434dd5e7984a1
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-c-amp"></a>Пространство имен Concurrency (C++ AMP)
Предоставляет классы и функции, которые ускоряют выполнение кода C++ на оборудовании с параллельными данными. Дополнительные сведения см. в разделе [Обзор C++ AMP](../cpp-amp-overview.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="namespaces"></a>Пространства имен  
  
|Имя|Описание|  
|----------|-----------------|  
|[Пространство имен Concurrency::Direct3D](concurrency-direct3d-namespace.md)|Предоставляет функции, поддерживающие взаимодействие D3D. Обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP и использование ресурсов, созданные в AMP в коде D3D, без создания промежуточных резервированием. Можно использовать C++ AMP постепенно ускорения вычислений разделы приложений DirectX и использовать D3D API на данные, полученные из AMP вычислений.|  
|[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)|Функции в `fast_math` пространства имен не совместимы с C99. Имеются только одиночной точности версии каждой функции. Эти функции используют встроенные функции DirectX, которые работают быстрее, чем соответствующие функции в `precise_math` пространства имен и расширенная поддержка двойной точности на сочетания клавиш не требуется, но они являются менее точными. Существуют две версии каждой функции для источника уровня совместимости с кодом C99; обе версии принимают и возвращают значения одинарной точности.|  
|[Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)|Предоставляет типы и функции, предназначенные для программирования графики.|  
|[Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)|Функции в `precise_math` пространства имен являются совместимыми C99. Включены одиночной точности и двойной точности версии каждой функции. Эти функции, включая функции одиночной точности — требуется расширенная поддержка двойной точности на сочетания клавиш.|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс Accelerator](accelerator-class.md)|Представляет абстракцию физических оптимизированных для DP вычислительного узла.|  
|[Класс accelerator_view](accelerator-view-class.md)|Представляет абстракцию виртуального устройства в ускорителе C++ AMP параллельными данными.|  
|[Класс accelerator_view_removed](accelerator-view-removed-class.md)|Исключение, возникающее при сбое внутренний вызов DirectX из-за механизм времени ожидания обнаружения и восстановления Windows.|  
|[Класс Array](array-class.md)|На статистических данных `accelerator_view` в области сетки. Это коллекция переменных, по одной для каждого элемента в домене сетки. Каждая переменная содержит значение, соответствующее типу некоторые C++.|  
|[Класс array_view](array-view-class.md)|Представляет представление данных в виде массива\<T, N настроек.|  
|[Класс completion_future](completion-future-class.md)|Представляет асинхронную операцию в C++ AMP будущего, которое соответствует.|  
|[Класс extent](extent-class.md)|Представляет вектор N целых значений, которые указывают границы многомерном пространстве, которое соответствует значение 0. Значения координат вектора упорядочиваются от наиболее важных до наименее важных. Например в декартовой системе координат трехмерном пространстве вектор экстент (7,5,3) представляет места, в котором координату z в диапазоне от 0 до 7, y координат в диапазоне от 0 до 5, и координаты x лежит в диапазоне от 0 до 3.|  
|[Класс index](index-class.md)|Определяет точку N-мерный индекса.|  
|[Класс invalid_compute_domain](invalid-compute-domain-class.md)|Исключение, возникающее, когда среде выполнения не удается запустить ядра с помощью вычислений домена, указанного в `parallel_for_each` вызова.|  
|[Класс out_of_memory](out-of-memory-class.md)|Исключение, возникающее при сбое метода из-за нехватки памяти системы или устройства.|  
|[Класс runtime_exception](runtime-exception-class.md)|Базовый тип для исключений в C++ AMP библиотеки.|  
|[Класс tile_barrier](tile-barrier-class.md)|Возможности класса, который только создаваемые системой и передается мозаичный `parallel_for_each` лямбда-выражения как часть `tiled_index` параметр. Он предоставляет один метод `wait()`, целью которого является выполнение потоков, выполняющихся в группе потока (плитки) синхронизации.|  
|[Класс tiled_extent](tiled-extent-class.md)|Объект `tiled_extent` объект `extent` объект от одного до трех измерений, подразделяет пространства экстента в одномерный массив двумерных и трехмерных плитки.|  
|[Класс tiled_index](tiled-index-class.md)|Предоставляет индекс в `tiled_grid` объекта. Этот класс содержит свойства для доступа к элементу относительно плитки локального источника и относительно глобального источника.|  
|[Класс uninitialized_object](uninitialized-object-class.md)|Исключение, возникающее при использовании неинициализированный объект.|  
|[Класс unsupported_feature](unsupported-feature-class.md)|Исключение, возникающее при использовании неподдерживаемой возможности.|  
  
### <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление access_type](concurrency-namespace-enums-amp.md#access_type)|Указывает тип данных доступа.|  
|[Перечисление queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)|Указывает режимы очереди, которые поддерживаются сочетания клавиш.|  
  
### <a name="operators"></a>Операторы  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[Оператор Operator == (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Определяет, равны ли указанные данные структуры.|  
|[оператор! =-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Определяет, равны ли структур данных.|  
|[Оператор Operator + (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Вычисляет сумму component-wise указанные аргументы.|  
|[Оператор Operator-(C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Component-wise расхождения между указанными аргументами.|  
|[оператор * оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Вычисляет произведение component-wise указанные аргументы.|  
|[оператор-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Вычисляет частное component-wise указанных аргументов.|  
|[Оператор Operator % (C++ AMP)](concurrency-namespace-operators-amp.md#operator_mod)|Вычисляет модуль первого указанного аргумента с помощью второго заданного аргумента.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к памяти.|  
|[Функция amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|Отменяет инициализацию среды выполнения C++ AMP.|  
|[Функция atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Перегружен. Если первое значение указанного сравнивает значение, хранящееся в указанном месте, второго заданного значения хранятся в том же расположении в виде атомарной операции.|  
|[Функция atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Перегружен. Задает значение, хранящееся в указанном месте указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Перегружен. Задает значение, хранящееся в указанном месте сумме этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `and` из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Перегружен. Уменьшает значение хранятся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|  
|[Функция atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Перегружен. Увеличивает значение, хранящееся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|  
|[Функция atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Перегружен. Задает значение, хранящееся в указанном месте в соответствии с большим из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Перегружен. Задает значение, хранящееся в указанной папке для меньшего из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `or` из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Перегружен. Задает значение, хранящееся в указанной папке для разность из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `xor` из этого значения и указанное значение в виде атомарной операции.|  
|[Copy-функция](concurrency-namespace-functions-amp.md#copy)|Копирует объект C++ AMP. Все синхронные данные передачи требований. Не удается скопировать данные, когда код выполняется код в ускорителя. Эта функция выглядит `copy(src, dest)`.|  
|[Функция copy_async](concurrency-namespace-functions-amp.md#copy_async)|Копирует объект C++ AMP и возвращает [completion_future](completion-future-class.md) , можно ожидать. Не удается скопировать данные, когда код выполняется на ускорителя. Эта функция выглядит `copy(src, dest)`.|  
|[Функция direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Прерывает выполнение функции, имеющей `restrict(amp)` предложения ограничения.|  
|[Функция direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Выводит форматированную строку в Visual Studio **вывода** окна и вызывает [runtime_exception](runtime-exception-class.md) исключение, которое имеет то же форматирование строки.|  
|[Функция direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Выводит форматированную строку в Visual Studio **вывода** окна. Он вызывается из функции с `restrict(amp)` предложения ограничения.|  
|[Функция global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Блокирует выполнение всех потоков в мозаике до обращения к памяти все глобальные завершена.|  
|[Функция parallel_for_each (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Выполняет функцию домене вычислений.|  
|[Функция tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Блокирует выполнение всех потоков в мозаике до `tile_static` завершили доступов к памяти.|  
  
## <a name="constants"></a>Константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа HLSL_MAX_NUM_BUFFERS](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Максимальное количество буферов, допустимых в DirectX.|  
|[Константа MODULENAME_MAX_LENGTH](concurrency-namespace-constants-amp.md#modulename_max_length)|Хранит Максимальная длина имени модуля. Это значение должно быть одинаковым на компилятор и среда выполнения.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
## <a name="see-also"></a>См. также  
 [Справочник (C++ AMP)](reference-cpp-amp.md)




