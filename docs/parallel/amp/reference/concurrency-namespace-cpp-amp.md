---
title: "Пространство имен Concurrency (C++ AMP) | Microsoft Docs"
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
  - "amp/Concurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency - пространство имен"
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пространство имен Concurrency (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Предоставляет классы и функции, которые ускоряют выполнение кода C++ на оборудовании с параллельными данными. Дополнительные сведения см. в разделе [Обзор C++ AMP](../../../parallel/amp/cpp-amp-overview.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Concurrency;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="namespaces"></a>Пространства имен  
  
|Имя|Описание|  
|----------|-----------------|  
|[Пространство имен Concurrency::Direct3D](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)|Предоставляет функции, поддерживающие взаимодействие D3D. Обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP и использование ресурсов, созданные в AMP в коде D3D, без создания промежуточных резервированием. Можно использовать C++ AMP постепенно ускорения вычислений разделы приложений DirectX и использовать D3D API на данные, полученные из AMP вычислений.|  
|[Пространство имен Concurrency::fast_math](../../../parallel/amp/reference/concurrency-fast-math-namespace.md)|Функции в `fast_math` пространства имен не совместимы с C99. Имеются только одиночной точности версии каждой функции. Эти функции используют встроенные функции DirectX, которые работают быстрее, чем соответствующие функции в `precise_math` пространства имен и расширенная поддержка двойной точности на сочетания клавиш не требуется, но они являются менее точными. Существуют две версии каждой функции для источника уровня совместимости с кодом C99; обе версии принимают и возвращают значения одинарной точности.|  
|[Пространство имен Concurrency::Graphics](../../../parallel/amp/reference/concurrency-graphics-namespace.md)|Предоставляет типы и функции, предназначенные для программирования графики.|  
|[Пространство имен Concurrency::precise_math](../Topic/Concurrency::precise_math%20Namespace.md)|Функции в `precise_math` пространства имен являются совместимыми C99. Включены одиночной точности и двойной точности версии каждой функции. Эти функции, включая функции одиночной точности — требуется расширенная поддержка двойной точности на сочетания клавиш.|  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс Accelerator](../../../parallel/amp/reference/accelerator-class.md)|Представляет абстракцию физических оптимизированных для DP вычислительного узла.|  
|[Класс accelerator_view](../Topic/accelerator_view%20Class.md)|Представляет абстракцию виртуального устройства в ускорителе C++ AMP параллельными данными.|  
|[Класс accelerator_view_removed](../../../parallel/amp/reference/accelerator-view-removed-class.md)|Исключение, возникающее при сбое внутренний вызов DirectX из-за механизм времени ожидания обнаружения и восстановления Windows.|  
|[Класс Array](../../../parallel/amp/reference/array-class.md)|На статистических данных `accelerator_view` в области сетки. Это коллекция переменных, по одной для каждого элемента в домене сетки. Каждая переменная содержит значение, соответствующее типу некоторые C++.|  
|[Класс array_view](../../../parallel/amp/reference/array-view-class.md)|Представляет представление данных в виде массива \< T, N >.|  
|[Класс completion_future](../Topic/completion_future%20Class.md)|Представляет асинхронную операцию в C++ AMP будущего, которое соответствует.|  
|[Класс Extent](../Topic/extent%20Class%20\(C++%20AMP\).md)|Представляет вектор N целых значений, которые указывают границы многомерном пространстве, которое соответствует значение 0. Значения координат вектора упорядочиваются от наиболее важных до наименее важных. Например в декартовой системе координат трехмерном пространстве вектор экстент (7,5,3) представляет места, в котором координату z в диапазоне от 0 до 7, y координат в диапазоне от 0 до 5, и координаты x лежит в диапазоне от 0 до 3.|  
|[Класс index](../../../parallel/amp/reference/index-class.md)|Определяет точку N-мерный индекса.|  
|[Класс invalid_compute_domain](../../../parallel/amp/reference/invalid-compute-domain-class.md)|Исключение, возникающее, когда среде выполнения не удается запустить ядра с помощью вычислений домена, указанного в `parallel_for_each` вызова.|  
|[Класс out_of_memory](../../../parallel/amp/reference/out-of-memory-class.md)|Исключение, возникающее при сбое метода из-за нехватки памяти системы или устройства.|  
|[Класс runtime_exception](../Topic/runtime_exception%20Class.md)|Базовый тип для исключений в C++ AMP библиотеки.|  
|[Класс tile_barrier](../Topic/tile_barrier%20Class.md)|Возможности класса, который только создаваемые системой и передается мозаичный `parallel_for_each` лямбда-выражения как часть `tiled_index` параметр. Он предоставляет один метод `wait()`, целью которого является выполнение потоков, выполняющихся в группе потока (плитки) синхронизации.|  
|[Класс tiled_extent](../../../parallel/amp/reference/tiled-extent-class.md)|Объект `tiled_extent` объект `extent` объект от одного до трех измерений, подразделяет пространства экстента в одномерный массив двумерных и трехмерных плитки.|  
|[Класс tiled_index](../../../parallel/amp/reference/tiled-index-class.md)|Предоставляет индекс в `tiled_grid` объекта. Этот класс содержит свойства для доступа к элементу относительно плитки локального источника и относительно глобального источника.|  
|[Класс uninitialized_object](../../../parallel/amp/reference/uninitialized-object-class.md)|Исключение, возникающее при использовании неинициализированный объект.|  
|[Класс unsupported_feature](../../../parallel/amp/reference/unsupported-feature-class.md)|Исключение, возникающее при использовании неподдерживаемой возможности.|  
  
### <a name="enumerations"></a>Перечисления  
  
|Имя|Описание|  
|----------|-----------------|  
|[Перечисление access_type](../Topic/access_type%20Enumeration.md)|Указывает тип данных доступа.|  
|[Перечисление queuing_mode](../../../parallel/amp/reference/queuing-mode-enumeration.md)|Указывает режимы очереди, которые поддерживаются сочетания клавиш.|  
  
### <a name="operators"></a>Операторы  
  
|Оператор|Описание|  
|--------------|-----------------|  
|[Оператор Operator == (C++ AMP)](../Topic/operator==%20Operator%20\(C++%20AMP\).md)|Определяет, равны ли указанные данные структуры.|  
|[оператор! =-оператор (C++ AMP)](../Topic/operator!=%20Operator%20\(C++%20AMP\).md)|Определяет, равны ли структур данных.|  
|[Оператор Operator + (C++ AMP)](../Topic/operator+%20Operator%20\(C++%20AMP\).md)|Вычисляет сумму component-wise указанные аргументы.|  
|[Оператор Operator-(C++ AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)1.md)|Component-wise расхождения между указанными аргументами.|  
|[оператор * оператор (C++ AMP)](../Topic/operator*%20Operator%20\(C++%20AMP\).md)|Вычисляет произведение component-wise указанные аргументы.|  
|[оператор-оператор (C++ AMP)](../Topic/operator-%20Operator%20\(C++%20AMP\)2.md)|Вычисляет частное component-wise указанных аргументов.|  
|[Оператор Operator % (C++ AMP)](../Topic/operator%25%20Operator%20\(C++%20AMP\).md)|Вычисляет модуль первого указанного аргумента с помощью второго заданного аргумента.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция all_memory_fence](../Topic/all_memory_fence%20Function.md)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к памяти.|  
|[Функция amp_uninitialize](../Topic/amp_uninitialize%20Function.md)|Отменяет инициализацию среды выполнения C++ AMP.|  
|[Функция atomic_compare_exchange](../Topic/atomic_compare_exchange%20Function.md)|Перегружен. Если первое значение указанного сравнивает значение, хранящееся в указанном месте, второго заданного значения хранятся в том же расположении в виде атомарной операции.|  
|[Функция atomic_exchange](../Topic/atomic_exchange%20Function%20\(C++%20AMP\).md)|Перегружен. Задает значение, хранящееся в указанном месте указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_add](../Topic/atomic_fetch_add%20Function%20\(C++%20AMP\).md)|Перегружен. Задает значение, хранящееся в указанном месте сумме этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_and](../Topic/atomic_fetch_and%20Function%20\(C++%20AMP\).md)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `and` из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_dec](../Topic/atomic_fetch_dec%20Function.md)|Перегружен. Уменьшает значение хранятся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|  
|[Функция atomic_fetch_inc](../Topic/atomic_fetch_inc%20Function.md)|Перегружен. Увеличивает значение, хранящееся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|  
|[Функция atomic_fetch_max](../Topic/atomic_fetch_max%20Function.md)|Перегружен. Задает значение, хранящееся в указанном месте в соответствии с большим из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_min](../Topic/atomic_fetch_min%20Function.md)|Перегружен. Задает значение, хранящееся в указанной папке для меньшего из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_or](../Topic/atomic_fetch_or%20Function%20\(C++%20AMP\).md)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `or` из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_sub](../Topic/atomic_fetch_sub%20Function%20\(C++%20AMP\).md)|Перегружен. Задает значение, хранящееся в указанной папке для разность из этого значения и указанное значение в виде атомарной операции.|  
|[Функция atomic_fetch_xor](../Topic/atomic_fetch_xor%20Function%20\(C++%20AMP\).md)|Перегружен. Задает значение, хранящееся в указанной папке для побитового `xor` из этого значения и указанное значение в виде атомарной операции.|  
|[Copy-функция](../Topic/copy%20Function.md)|Копирует объект C++ AMP. Все синхронные данные передачи требований. Не удается скопировать данные, когда код выполняется код в ускорителя. Эта функция выглядит `copy(src, dest)`.|  
|[Функция copy_async](../Topic/copy_async%20Function.md)|Копирует объект C++ AMP и возвращает [completion_future](../Topic/completion_future%20Class.md) можно ожидать. Не удается скопировать данные, когда код выполняется на ускорителя. Эта функция выглядит `copy(src, dest)`.|  
|[Функция direct3d_abort](../Topic/direct3d_abort%20Function.md)|Прерывает выполнение функции, имеющей `restrict(amp)` предложения ограничения.|  
|[Функция direct3d_errorf](../Topic/direct3d_errorf%20Function.md)|Выводит форматированную строку в Visual Studio **вывода** окна и вызывает [runtime_exception](../Topic/runtime_exception%20Class.md) исключение, которое имеет то же форматирование строки.|  
|[Функция direct3d_printf](../Topic/direct3d_printf%20Function.md)|Выводит форматированную строку в Visual Studio **вывода** окна. Он вызывается из функции с `restrict(amp)` предложения ограничения.|  
|[Функция global_memory_fence](../Topic/global_memory_fence%20Function.md)|Блокирует выполнение всех потоков в мозаике до обращения к памяти все глобальные завершена.|  
|[Функция parallel_for_each (C++ AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)|Выполняет функцию домене вычислений.|  
|[Функция tile_static_memory_fence](../Topic/tile_static_memory_fence%20Function.md)|Блокирует выполнение всех потоков в мозаике до `tile_static` завершили доступов к памяти.|  
  
## <a name="constants"></a>Константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа HLSL_MAX_NUM_BUFFERS](../Topic/HLSL_MAX_NUM_BUFFERS%20Constant.md)|Максимальное количество буферов, допустимых в DirectX.|  
|[Константа MODULENAME_MAX_LENGTH](../Topic/MODULENAME_MAX_LENGTH%20Constant.md)|Хранит Максимальная длина имени модуля. Это значение должно быть одинаковым на компилятор и среда выполнения.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp.h  
  
## <a name="see-also"></a>См. также  
 [Справочник (C++ AMP)](../../../parallel/amp/reference/reference-cpp-amp.md)



