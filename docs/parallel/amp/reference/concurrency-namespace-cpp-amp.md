---
title: Пространство имен Concurrency (C++ AMP)
ms.date: 11/04/2016
f1_keywords:
- AMP/Concurrency
helpviewer_keywords:
- Concurrency namespace
ms.assetid: b5aab265-3bac-42c5-8ead-f92ce05ef267
ms.openlocfilehash: e0870eb046f1cec091a72d49c94a2fea41484340
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278695"
---
# <a name="concurrency-namespace-c-amp"></a>Пространство имен Concurrency (C++ AMP)

Предоставляет классы и функции, которые ускоряют выполнение кода C++ на оборудовании с параллельной обработки данных. Дополнительные сведения см. в разделе [Обзор C++ AMP](../cpp-amp-overview.md)

## <a name="syntax"></a>Синтаксис

```
namespace Concurrency;
```

## <a name="members"></a>Члены

### <a name="namespaces"></a>Пространства имен

|Имя|Описание|
|----------|-----------------|
|[Пространство имен Concurrency::direct3d](concurrency-direct3d-namespace.md)|Предоставляет функции, которые поддерживают взаимодействие с D3D. Позволяет прозрачным образом использовать D3D-ресурсы для вычислений в AMP-коде и использование ресурсов, созданные в AMP в коде D3D без создания промежуточных резервных копий. Можно использовать C++ AMP инкрементально ускорять вычислительно части DirectX приложений и использовать D3D API на данных, полученных из AMP вычислений.|
|[Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)|Функции в `fast_math` пространства имен не совместимы с C99. Предоставляются только версии одиночной точности каждой функции. Эти функции используют встроенные функции DirectX, которые работают быстрее, чем соответствующие функции в `precise_math` пространства имен и не требуют расширенной поддержки двойной точности в ускорителе, но они являются менее точными. Существует две версии каждой функции для источника на уровне совместимости с кодом C99; обе версии принимают и возвращают значения одиночной точности.|
|[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)|Предоставляет типы и функции, которые предназначены для программирования графики.|
|[Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)|Функции в `precise_math` пространства имен являются совместимыми C99. Включены версии одинарной и двойной точности каждой функции. Эти функции — к ним относятся функции одиночной точности, требуют расширенной поддержки двойной точности в ускорителе.|

### <a name="classes"></a>Классы

|Имя|Описание:|
|----------|-----------------|
|[Класс accelerator](accelerator-class.md)|Представляет абстракцию физического DP-оптимизированного вычислительного узла.|
|[Класс accelerator_view](accelerator-view-class.md)|Представляет абстракцию виртуального устройства на ускорителе с параллельными данными C++ AMP.|
|[Класс accelerator_view_removed](accelerator-view-removed-class.md)|Исключение, возникающее при сбое основного вызова DirectX из-за механизм времени ожидания обнаружения и восстановления Windows.|
|[Класс array](array-class.md)|Это агрегат данных в `accelerator_view` в домене сетки. Это коллекция переменных, по одной для каждого элемента в домене сетки. Каждая переменная содержит значение, соответствующее некоторому типу C++.|
|[Класс array_view](array-view-class.md)|Представляет представление данных в массиве\<T, N >.|
|[Класс completion_future](completion-future-class.md)|Представляет фьючерс, соответствующей асинхронной операции C++ AMP.|
|[Класс extent](extent-class.md)|Представляет вектор из N целочисленных значений, которые определяют границы N-мерного пространства с началом координат в 0. Значения в координатном векторе упорядочены от наиболее важных до наименее важных. Например в декартовой системе координат трехмерном пространстве, вектор (7,5,3) представляет пространство, в котором Координата по оси z в диапазоне от 0 до 7, y координат в диапазоне от 0 до 5, и по оси x в диапазоне от 0 до 3.|
|[Класс index](index-class.md)|Определяет N-мерную точку индекса.|
|[Класс invalid_compute_domain](invalid-compute-domain-class.md)|Исключение, возникающее, когда среда выполнения не может запустить ядро с помощью вычислительного домена, указанного в `parallel_for_each` место вызова.|
|[Класс out_of_memory](out-of-memory-class.md)|Исключение, возникающее при сбое метода из-за нехватки памяти системы или устройства.|
|[Класс runtime_exception](runtime-exception-class.md)|Базовый тип для исключений в библиотеке C++ AMP.|
|[Класс tile_barrier](tile-barrier-class.md)|Класс возможности, который только создаваемые системой и передается выражению `parallel_for_each` лямбда-выражения, как часть `tiled_index` параметра. Он предоставляет один метод `wait()`, цель которого — синхронизировать выполнение потоков, работающих под управлением в группе потоков (мозаике).|
|[Класс tiled_extent](tiled-extent-class.md)|Объект `tiled_extent` объект `extent` объект от одного до трех измерений, подразделяет пространство на одномерный, двухмерный или трехмерную мозаику.|
|[Класс tiled_index](tiled-index-class.md)|Предоставляет индекс в `tiled_grid` объекта. Этот класс содержит свойства для доступа к элементу относительно локального начального положения плитки и относительно глобального начального положения.|
|[Класс uninitialized_object](uninitialized-object-class.md)|Исключение, возникающее, когда используется неинициализированный объект.|
|[Класс unsupported_feature](unsupported-feature-class.md)|Исключение, возникающее, когда используется неподдерживаемое свойство.|

### <a name="enumerations"></a>Перечисления

|Имя|Описание|
|----------|-----------------|
|[Перечисление access_type](concurrency-namespace-enums-amp.md#access_type)|Указывает тип доступа к данным.|
|[Перечисление queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)|Определяет режимы организации очереди, которые поддерживаются в сочетании клавиш.|

### <a name="operators"></a>Операторы

|Оператор|Описание:|
|--------------|-----------------|
|[оператор ==-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_eq_eq)|Определяет, равны ли две заданных структуры данных.|
|[оператор! =-оператор (C++ AMP)](concurrency-namespace-operators-amp.md#operator_neq)|Определяет, являются ли две заданных структуры данных неравными.|
|[Оператор Operator + (C++ AMP)](concurrency-namespace-operators-amp.md#operator_add)|Вычисляет покомпонентную сумму двух заданных аргументов.|
|[Оператор Operator-(C++ AMP)](concurrency-namespace-operators-amp.md#operator-)|Вычисляет разность между указанными аргументами.|
|[Оператор * Operator (C++ AMP)](concurrency-namespace-operators-amp.md#operator_star)|Вычисляет покомпонентное произведение заданных аргументов.|
|[Оператор / Operator (C++ AMP)](concurrency-namespace-operators-amp.md#operator_div)|Вычисляет покомпонентное частное двух заданных аргументов.|
|[Оператор Operator (C++ AMP) %](concurrency-namespace-operators-amp.md#operator_mod)|Вычисляет остаток деления первого заданного аргумента с помощью второго заданного аргумента.|

### <a name="functions"></a>Функции

|Имя|Описание:|
|----------|-----------------|
|[all_memory_fence](concurrency-namespace-functions-amp.md#all_memory_fence)|Блокирует выполнение всех потоков в плитке, пока не будут завершены все доступы к памяти.|
|[amp_uninitialize](concurrency-namespace-functions-amp.md#amp_uninitialize)|Отменяет инициализацию среды выполнения C++ AMP.|
|[atomic_compare_exchange](concurrency-namespace-functions-amp.md#atomic_compare_exchange)|Перегружен. Если значение, хранящееся в указанном месте оказывается равным первому указанному значению, то второе указанное значение сохраняется в том же расположении, что атомарной операции.|
|[atomic_exchange](concurrency-namespace-functions-amp.md#atomic_exchange)|Перегружен. Задает значение, хранящееся в указанном расположении указанное значение в виде атомарной операции.|
|[atomic_fetch_add](concurrency-namespace-functions-amp.md#atomic_fetch_add)|Перегружен. Задает значение, хранящееся в указанном расположении сумме этого значения и значения, заданного в виде атомарной операции.|
|[atomic_fetch_and](concurrency-namespace-functions-amp.md#atomic_fetch_and)|Перегружен. Задает значение, сохраненное в заданном расположении, в побитовое `and` этого значения и заданное значение в качестве атомарной операции.|
|[atomic_fetch_dec](concurrency-namespace-functions-amp.md#atomic_fetch_dec)|Перегружен. Уменьшает значение хранятся в указанном месте и сохраняет результат в том же расположении в виде атомарной операции.|
|[atomic_fetch_inc](concurrency-namespace-functions-amp.md#atomic_fetch_inc)|Перегружен. Увеличивает значение, хранящееся в указанном месте и сохраняет результат в том же расположении, что атомарной операции.|
|[atomic_fetch_max](concurrency-namespace-functions-amp.md#atomic_fetch_max)|Перегружен. Задает значение, сохраненное в заданном расположении в соответствии с большим этого значения и заданное значение в качестве атомарной операции.|
|[atomic_fetch_min](concurrency-namespace-functions-amp.md#atomic_fetch_min)|Перегружен. Задает значение, сохраненное в заданном расположении в наименьшее из этого значения и заданное значение в качестве атомарной операции.|
|[atomic_fetch_or](concurrency-namespace-functions-amp.md#atomic_fetch_or)|Перегружен. Задает значение, сохраненное в заданном расположении, в побитовое `or` этого значения и заданное значение в качестве атомарной операции.|
|[atomic_fetch_sub](concurrency-namespace-functions-amp.md#atomic_fetch_sub)|Перегружен. Задает значение, хранящееся в указанном месте на различие этого значения и заданное значение в виде атомарной операции.|
|[atomic_fetch_xor](concurrency-namespace-functions-amp.md#atomic_fetch_xor)|Перегружен. Задает значение, сохраненное в заданном расположении, в побитовое `xor` этого значения и заданное значение в качестве атомарной операции.|
|[copy](concurrency-namespace-functions-amp.md#copy)|Копирует объект C++ AMP. Выполнены все требования синхронной передачи данных. Не удается скопировать данные, когда код выполняется код на ускорителе. Эта функция выглядит `copy(src, dest)`.|
|[copy_async](concurrency-namespace-functions-amp.md#copy_async)|Копирует объект C++ AMP и возвращает [completion_future](completion-future-class.md) , можно использовать для ожидания. Не удается скопировать данные, когда код выполняется на ускорителе. Эта функция выглядит `copy(src, dest)`.|
|[direct3d_abort](concurrency-namespace-functions-amp.md#direct3d_abort)|Прерывает выполнение функции, которая имеет `restrict(amp)` предложение ограничения.|
|[direct3d_errorf](concurrency-namespace-functions-amp.md#direct3d_errorf)|Выводит отформатированную строку в Visual Studio **вывода** окна и вызывает [runtime_exception](runtime-exception-class.md) строка исключение, которое имеет одинаковое форматирование.|
|[direct3d_printf](concurrency-namespace-functions-amp.md#direct3d_printf)|Выводит отформатированную строку в Visual Studio **вывода** окна. Он вызывается из функции, которая имеет `restrict(amp)` предложение ограничения.|
|[global_memory_fence](concurrency-namespace-functions-amp.md#global_memory_fence)|Блокирует выполнение всех потоков в плитке до всех глобального доступа к памяти будет завершена.|
|[parallel_for_each функции (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)|Выполняет функцию в вычислительном домене.|
|[tile_static_memory_fence](concurrency-namespace-functions-amp.md#tile_static_memory_fence)|Блокирует выполнение всех потоков в плитке до `tile_static` будет завершено обращение к памяти.|

## <a name="constants"></a>Константы

|Имя|Описание:|
|----------|-----------------|
|[Константа HLSL_MAX_NUM_BUFFERS](concurrency-namespace-constants-amp.md#hlsl_max_num_buffers)|Максимальное количество буферов, допускаемое DirectX.|
|[Modulename_max_length-константа](concurrency-namespace-constants-amp.md#modulename_max_length)|Хранит максимальную длину имени модуля. Это значение должно быть одинаковым на компилятор и среда выполнения.|

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

## <a name="see-also"></a>См. также

[Справочник (C++ AMP)](reference-cpp-amp.md)
