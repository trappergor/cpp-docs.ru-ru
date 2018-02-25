---
title: "Пространство имен Concurrency (C++ AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- AMP/Concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a9f82baade21cdbde41fc49fd0bfe6163c0f6af
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="concurrency-namespace-c-amp"></a>Пространство имен Concurrency (C++ AMP)
Предоставляет классы и функции, ускоряющих выполнение кода C++ на оборудовании с параллельными данными. Дополнительные сведения см. в разделе [Обзор C++ AMP](../cpp-amp-overview.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="namespaces"></a>Пространства имен  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)|Предоставляет функции, поддерживающие взаимодействие D3D. Обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP и использование ресурсов, созданные в AMP в коде D3D, не создавая промежуточные резервированием. C++ AMP можно использовать для добавочного ускорения разделах ресурсоемких приложений DirectX и использовать этот API D3D в формируемые AMP вычисления данных.|  
|[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)|Функции в `fast_math` пространства имен не удовлетворяют требованиям C99. Имеются только одинарной точности версии каждой функции. Эти функции используют встроенные функции DirectX, которые работают быстрее, чем соответствующие функции в `precise_math` пространства имен и не требуют расширенной поддержки двойной точности на сочетания клавиш, но они являются менее точными. Существуют две версии каждой функции для источника уровня совместимости с кодом C99; обе версии принимают и возвращают значения одинарной точности.|  
|[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)|Предоставляет типы и функции, предназначенные для программирования графики.|  
|[Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)|Функции в `precise_math` пространства имен являются совместимыми C99. Числа одинарной точности и двойной точности версии каждой функции включены. Эти функции — Сюда входят функции одиночной точности, требуется расширенная поддержка двойной точности на сочетания клавиш.|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Класс accelerator](accelerator-class.md)|Представляет абстракцию физического оптимизированных для обработки Документов вычислительного узла.|  
|[Класс accelerator_view](accelerator-view-class.md)|Представляет виртуальное устройство абстракции ускорителем C++ AMP параллельными данными.|  
|[Класс accelerator_view_removed](accelerator-view-removed-class.md)|Исключение, возникающее при сбое внутренний вызов DirectX из-за механизм времени ожидания обнаружения и восстановления Windows.|  
|[Класс array](array-class.md)|На статистических данных `accelerator_view` в области сетки. Представляет коллекцию переменных, по одной для каждого элемента в домене сетки. Каждая переменная содержит значение, соответствующее типу некоторые C++.|  
|[Класс array_view](array-view-class.md)|Представляет представление данных в виде массива\<T, N >.|  
|[Класс completion_future](completion-future-class.md)|Представляет будущее, который соответствует асинхронной операции C++ AMP.|  
|[Класс extent](extent-class.md)|Представляет вектор N целочисленных значений, которые указывают границы N-мерном пространстве, который соответствует значение 0. Значения координат вектора упорядочиваются от наиболее важных до наименее важных. Например в декартовой системе координат объемного пространстве, вектор экстент (7,5,3) представляет место, в котором значение координаты z в диапазоне от 0 до 7, y координат лежит в диапазоне от 0 до 5, и по оси x в диапазоне от 0 до 3.|  
|[Класс index](index-class.md)|Определяет точку многомерном индекса.|  
|[Класс invalid_compute_domain](invalid-compute-domain-class.md)|Исключение, возникающее, когда среда выполнения не может запустить ядро, используя указанные в домене вычислений `parallel_for_each` место вызова.|  
|[Класс out_of_memory](out-of-memory-class.md)|Исключение, возникающее при сбое метода из-за недостатка памяти системы или устройства.|  
|[Класс runtime_exception](runtime-exception-class.md)|Базовый тип для исключений C++ AMP библиотеки.|  
|[Класс tile_barrier](tile-barrier-class.md)|Возможность класса, который только создаваемыми системой и передается Мозаичная `parallel_for_each` лямбда-выражения в рамках `tiled_index` параметра. Он предоставляет один метод `wait()`, целью которого является синхронизации выполнение потоков, выполняющихся в группы потоков (плитки).|  
|[Класс tiled_extent](tiled-extent-class.md)|Объект `tiled_extent` объект `extent` объект одного до трех измерений, который позволяет разбить пространства экстента в одномерный массив, двумерный или трехмерного плиток.|  
|[Класс tiled_index](tiled-index-class.md)|Предоставляет индекс в `tiled_grid` объекта. Этот класс содержит свойства для доступа к элементу относительно Плитка локального источника, так и относительно глобального источника.|  
|[Класс uninitialized_object](uninitialized-object-class.md)|Исключение, возникающее при использовании неинициализированного объекта.|  
|[Класс unsupported_feature](unsupported-feature-class.md)|Исключение, возникающее при использовании неподдерживаемой возможности.|  
  
### <a name="enumerations"></a>Перечисления  
  
|name|Описание:|  
|----------|-----------------|  
|[access_type Enumeration](concurrency-namespace-enums-amp.md#access_type)|Указывает тип доступа к данных.|  
|[queuing_mode Enumeration](concurrency-namespace-enums-amp.md#queuing_mode)|Указывает режимы очередей, которые поддерживаются сочетания клавиш.|  
  
### <a name="operators"></a>Операторы  
  
|Оператор|Описание:|  
|--------------|-----------------|  
|[оператор ==-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Определяет, равны ли указанные данные структуры.|  
|[оператор! =-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Определяет, равны ли указанные данные структуры.|  
|[Оператор Operator + (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Вычисляет сумму component-wise указанных аргументов.|  
|[Оператор Operator-(C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Вычисляет component-wise различие между указанными аргументами.|  
|[оператор * оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Вычисляет произведение component-wise указанные аргументы.|  
|[оператор-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Вычисляет частное component-wise указанные аргументы.|  
|[Оператор Operator (C++ AMP) %](concurrency-namespace-operators-amp.md#operator_mod)|Вычисляет модуль первого аргумента, указанного с помощью второго заданного аргумента.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание:|  
|----------|-----------------|  
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все попытки доступа к памяти.|  
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|Отменяет инициализацию среды выполнения C++ AMP.|  
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Перегружен. Если значение, хранящееся в указанном месте сравнивает его с первого указанного значения, второго заданного значения хранятся в том же расположении в виде атомарной операции.|  
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Перегружен. Задает значение, хранящееся в указанном месте с указанным значением в виде атомарной операции.|  
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Перегружен. Задает значение, хранящееся в указанном месте сумме этого значения и указанного значения в виде атомарной операции.|  
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `and` из этого значения и указанное значение в виде атомарной операции.|  
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Перегружен. Уменьшает значение хранятся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|  
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Перегружен. Увеличивает значение, хранящееся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|  
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Перегружен. Задает значение, хранящееся в указанном месте в соответствии с большим из этого значения и указанное значение в виде атомарной операции.|  
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Перегружен. Задает значение, хранящееся в указанной папке для меньшего из этого значения и указанное значение в виде атомарной операции.|  
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `or` из этого значения и указанное значение в виде атомарной операции.|  
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Перегружен. Задает значение, хранящееся в указанной папке для разница этого значения и указанного значения в виде атомарной операции.|  
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `xor` из этого значения и указанное значение в виде атомарной операции.|  
|[copy](concurrency-namespace-functions-amp.md#copy)|Копирует объект C++ AMP. Все синхронные данные передачи требований. Не удается скопировать данные, если код выполняется на ускорителе кода. Эта функция выглядит `copy(src, dest)`.|  
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|Копирует объект C++ AMP и возвращает [completion_future](completion-future-class.md) , можно ожидать. Не удается скопировать данные, если код выполняется на ускорителе. Эта функция выглядит `copy(src, dest)`.|  
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Прерывает выполнение функции, которая имеет `restrict(amp)` предложения ограничения.|  
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Выводит форматированную строку в Visual Studio **вывода** окна и вызывает [runtime_exception](runtime-exception-class.md) исключение, которое имеет одинаковое форматирование строк.|  
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Выводит форматированную строку в Visual Studio **вывода** окна. Он вызывается из функции, которая имеет `restrict(amp)` предложения ограничения.|  
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Блокирует выполнение всех потоков в мозаике до обращения к памяти все глобальные завершена.|  
|[parallel_for_each функции (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Выполняет функцию в домене вычислений.|  
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Блокирует выполнение всех потоков в мозаике до `tile_static` обращений к памяти будут завершены.|  
  
## <a name="constants"></a>Константы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[HLSL_MAX_NUM_BUFFERS Constant](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Максимальное количество буферов, допустимых в DirectX.|  
|[Константа MODULENAME_MAX_LENGTH](concurrency-namespace-constants-amp.md#modulename_max_length)|Хранит Максимальная длина имени модуля. Это значение должно быть одинаковым на компилятор и среда выполнения.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
## <a name="see-also"></a>См. также  
 [Справочник (C++ AMP)](reference-cpp-amp.md)



