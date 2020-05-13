---
title: Функции пространства имен Concurrency (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::all_memory_fence
- amp/Concurrency::atomic_compare_exchange
- amp/Concurrency::atomic_fetch_dec
- amp/Concurrency::atomic_fetch_max
- amp/Concurrency::atomic_fetch_min
- amp/Concurrency::copy
- amp/Concurrency::direct3d_abort
- amp/Concurrency::direct3d_printf
- amp/Concurrency::global_memory_fence
- amp/Concurrency::tile_static_memory_fence
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
ms.openlocfilehash: 1187b745a6d8c903c22958185be8d98a6e3d0204
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376351"
---
# <a name="concurrency-namespace-functions-amp"></a>Функции пространства имен Concurrency (AMP)

||||
|-|-|-|
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|
|[Функция atomic_exchange (C++ AMP)](#atomic_exchange)|[Функция atomic_fetch_add (C++ AMP)](#atomic_fetch_add)|[Функция atomic_fetch_and (C++ AMP)](#atomic_fetch_and)|
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|
|[atomic_fetch_min](#atomic_fetch_min)|[Функция atomic_fetch_or (C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub функция (СЗ АМП)](#atomic_fetch_sub)|
|[Функция atomic_fetch_xor (C++ AMP)](#atomic_fetch_xor)|[Копировать](#copy)|[copy_async](#copy_async)|
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|
|[global_memory_fence](#global_memory_fence)|[Функция parallel_for_each (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|

## <a name="all_memory_fence"></a><a name="all_memory_fence"></a>all_memory_fence

Блоки выполнения всех потоков в плитке до тех пор, пока все доступы к памяти не будут завершены. Это гарантирует, что все доступы к памяти будут видны другим потокам в плитке потока и выполняются в порядке программы.

```cpp
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Barrier*<br/>
Объект `tile_barrier` .

## <a name="amp_uninitialize"></a><a name="amp_uninitialize"></a>amp_uninitialize

Не инициирует время выполнения amp AMP. Это законно, чтобы вызвать эту функцию несколько раз в течение срока действия приложений. Вызов любого API АМП после вызова этой функции будет репрефализации времени выполнения C'AMP. Обратите внимание, что использование объектов C AMP в рамках вызовов этой функции является незаконным, и это приведет к неопределенному поведению. Кроме того, одновременное вызов этой функции и любых других АПП является незаконным и приведет к неопределенным поведением.

```cpp
void __cdecl amp_uninitialize();
```

## <a name="atomic_compare_exchange"></a><a name="atomic_compare_exchange"></a>atomic_compare_exchange

Атомно сравнивает значение, хранящееся в месте памяти, указанном в первом аргументе равенства, со значением второго указанного аргумента, и если значения одинаковы, значение в месте памяти изменяется на значение третьего указанного аргумента.

```cpp
inline bool atomic_compare_exchange(
    _Inout_ int* _Dest,
    _Inout_ int* _Expected_value,
    int value
    ) restrict(amp)

inline bool atomic_compare_exchange(
    _Inout_ unsigned int* _Dest,
    _Inout_ unsigned int* _Expected_value,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Место, с которого считывалось одно из значений, которое необходимо сравнить, и к которому должно храниться новое значение, если таковое.

*_Expected_value*<br/>
Место, с которого считывалось второе значение для сопоставления.

*value*<br/>
Значение, необходимое для хранения в `_Dest` месте `_Dest` памяти, указанном в случае, `_Expected_value`равному.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если операция прошла успешно; в противном случае, **ложные**.

## <a name="atomic_exchange-function-c-amp"></a><a name="atomic_exchange"></a>atomic_exchange функция (СЗ АМП)

Устанавливает значение местоположения назначения как атомную операцию.

```cpp
inline int atomic_exchange(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_exchange(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)

inline float atomic_exchange(
    _Inout_ float* _Dest,
    float value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Указатель к месту назначения.

*value*<br/>
Новое значение.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение местоположения назначения.

## <a name="atomic_fetch_add-function-c-amp"></a><a name="atomic_fetch_add"></a>atomic_fetch_add функция (СЗ АМП)

Атомно едят значение к значению местоположения памяти.

```cpp
inline int atomic_fetch_add(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_add(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Указатель на место памяти.

*value*<br/>
Добавляемое значение.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение местоположения памяти.

## <a name="atomic_fetch_and-function-c-amp"></a><a name="atomic_fetch_and"></a>функция atomic_fetch_and (СЗ АМП)

Атомно выполняет bitwise и операции значение и значение местоположения памяти.

```cpp
inline int atomic_fetch_and(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_and(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Указатель на место памяти.

*value*<br/>
Значение для использования в bitwise и расчета.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение местоположения памяти.

## <a name="atomic_fetch_dec"></a><a name="atomic_fetch_dec"></a>atomic_fetch_dec

Атомно утилищает значение, хранящееся в указанном месте памяти.

```cpp
inline int atomic_fetch_dec(_Inout_ int* _Dest
    ) restrict(amp)

inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Расположение в памяти значения, подаваемый в decremented.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение, хранящееся в месте памяти.

## <a name="atomic_fetch_inc"></a><a name="atomic_fetch_inc"></a>atomic_fetch_inc

Атомно приращения значения, хранящегося в указанном месте памяти.

```cpp
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Расположение в памяти значения, подаваемых.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение, хранящееся в месте памяти.

## <a name="atomic_fetch_max"></a><a name="atomic_fetch_max"></a>atomic_fetch_max

Атомно вычисляет максимальное значение между значением, хранящимся в месте памяти, указанном в первом аргументе, и значением, указанным во втором аргументе, и сохраняет его в том же месте памяти.

```cpp
inline int atomic_fetch_max(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_max(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Место, с которого считывалось одно из значений, которое необходимо сравнить, и в котором должен храниться максимум из двух значений.

*value*<br/>
Значение, необходимое для сопоставления со значением в указанном месте.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение, хранящееся в указанном месте.

## <a name="atomic_fetch_min"></a><a name="atomic_fetch_min"></a>atomic_fetch_min

Атомически вычисляет минимальное значение между местом памяти, указанным в первом аргументе, и значением, указанным во втором аргументе, и сохраняет его в том же месте памяти.

```cpp
inline int atomic_fetch_min(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_min(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Место, с которого считывалось одно из значений, которое необходимо сравнить, и к которому должен храниться минимум двух значений.

*value*<br/>
Значение, необходимое для сопоставления со значением в указанном месте.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение, хранящееся в указанном месте.

## <a name="atomic_fetch_or-function-c-amp"></a><a name="atomic_fetch_or"></a>функция atomic_fetch_or (СЗ АМП)

Атомно выполняет битовую или операцию со значением и значением местоположения памяти.

```cpp
inline int atomic_fetch_or(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_or(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Указатель на место памяти.

*value*<br/>
Значение для использования в битом или расчете.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение местоположения памяти.

## <a name="atomic_fetch_sub-function-c-amp"></a><a name="atomic_fetch_sub"></a>atomic_fetch_sub функция (СЗ АМП)

Атомически вычитает значение из местоположения памяти.

```cpp
inline int atomic_fetch_sub(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_sub(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Указатель к месту назначения.

*value*<br/>
Значение, подаваемые для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение местоположения памяти.

## <a name="atomic_fetch_xor-function-c-amp"></a><a name="atomic_fetch_xor"></a>atomic_fetch_xor функция (СЗ АМП)

Атомно выполняет bitwise XOR операции значения и местопамятии памяти.

```cpp
inline int atomic_fetch_xor(
    _Inout_ int* _Dest,
    int value
    ) restrict(amp)

inline unsigned int atomic_fetch_xor(
    _Inout_ unsigned int* _Dest,
    unsigned int value
    ) restrict(amp)
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Указатель на место памяти.

*value*<br/>
Значение для использования в расчете XOR.

### <a name="return-value"></a>Возвращаемое значение

Исходное значение местоположения памяти.

## <a name="copy"></a><a name="copy"></a>Копировать

Копирует объект АМП СЗ. Все требования по передаче синхронных данных удовлетворяются. Вы не можете копировать данные при запуске кода на ускорителе. Общая форма этой функции `copy(src, dest)`.

```cpp
template <typename value_type, int _Rank>
void copy(
    const array<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    array<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
void copy(
    const array<value_type, _Rank>& _Src,
   OutputIterator _DestIter);

template <typename value_type, int _Rank>
void copy(
    const array<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<const value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<const value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
void copy(
    const array_view<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    InputIterator _SrcLast,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
void copy(
    InputIterator _SrcFirst,
    array_view<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
void copy(
    const array_view<value_type, _Rank>& _Src,
    OutputIterator _DestIter);
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Объект для копирования.

*_DestIter*<br/>
Итератор вывода в начальное положение в пункте назначения.

*Inputiterator*<br/>
Тип итератора ввода.

*Выводитатор*<br/>
Тип итератора вывода.

*_Rank*<br/>
Ранг объекта для копирования или объекта для копирования.

*_Src*<br/>
Для возражения против копирования.

*_SrcFirst*<br/>
Начальный итератор в исходный контейнер.

*_SrcLast*<br/>
Окончание итератора в исходный контейнер.

*Value_type*<br/>
Тип данных элементов, которые копируются.

## <a name="copy_async"></a><a name="copy_async"></a>copy_async

Копирует объект C' AMP и возвращает [completion_future](completion-future-class.md) объект, который можно ждать. Вы не можете копировать данные при запуске кода на ускорителе.  Общая форма этой функции `copy(src, dest)`.

```cpp
template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,
    array<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst,
    array<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src, OutputIterator _DestIter);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,
    array<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<const value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst, InputIterator _SrcLast,
    array_view<value_type, _Rank>& _Dest);

template <typename InputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(InputIterator _SrcFirst,
    array_view<value_type, _Rank>& _Dest);

template <typename OutputIterator, typename value_type, int _Rank>
concurrency::completion_future copy_async(
    const array_view<value_type, _Rank>& _Src, OutputIterator _DestIter);
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Объект для копирования.

*_DestIter*<br/>
Итератор вывода в начальное положение в пункте назначения.

*Inputiterator*<br/>
Тип итератора ввода.

*Выводитатор*<br/>
Тип итератора вывода.

*_Rank*<br/>
Ранг объекта для копирования или объекта для копирования.

*_Src*<br/>
Для возражения против копирования.

*_SrcFirst*<br/>
Начальный итератор в исходный контейнер.

*_SrcLast*<br/>
Окончание итератора в исходный контейнер.

*Value_type*<br/>
Тип данных элементов, которые копируются.

### <a name="return-value"></a>Возвращаемое значение

А, `future<void>` что можно ждать.

## <a name="direct3d_abort"></a><a name="direct3d_abort"></a>direct3d_abort

Прерывает выполнение функции с предложением ограничения `restrict(amp)` . Когда среда выполнения AMP обнаруживает вызов, она порождает исключение [runtime_exception](runtime-exception-class.md) с таким сообщением об ошибке: "Средство программной прорисовки: обнаружена инструкция прекращения работы шейдера".

```cpp
void direct3d_abort() restrict(amp);
```

## <a name="direct3d_errorf"></a><a name="direct3d_errorf"></a>direct3d_errorf

Печать отформатированный строки к выходу окна Visual Studio. Он вызывается из функции с оговоркой об ограничении. `restrict(amp)` Когда время выполнения AMP обнаруживает вызов, оно вызывает [runtime_exception](runtime-exception-class.md) исключение с той же строкой форматирования.

```cpp
void direct3d_errorf(
    const char *,
...) restrict(amp);
```

## <a name="direct3d_printf"></a><a name="direct3d_printf"></a>direct3d_printf

Печать отформатированный строки к выходу окна Visual Studio. Он вызывается из функции с оговоркой об ограничении. `restrict(amp)`

```cpp
void direct3d_printf(
    const char *,
...) restrict(amp);
```

## <a name="global_memory_fence"></a><a name="global_memory_fence"></a>global_memory_fence

Блоки выполнения всех потоков в плитке до тех пор, пока все глобальные доступы к памяти не будут завершены. Это гарантирует, что глобальные доступы к памяти будут видны другим потокам в плитке потока и выполняются в порядке программы.

```cpp
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Barrier*<br/>
Объект tile_barrier

## <a name="parallel_for_each-function-c-amp"></a><a name="parallel_for_each"></a>parallel_for_each функция (СЗ АМП)

Запускает функцию в домене вычислений. Для получения более [подробной](../../../parallel/amp/cpp-amp-overview.md)информации см.

```cpp
template <int _Rank, typename _Kernel_type>
void parallel_for_each(
    const extent<_Rank>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
   const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, typename _Kernel_type>
void parallel_for_each(
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, typename _Kernel_type>
void parallel_for_each(
    const tiled_extent<_Dim0>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Rank, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const extent<_Rank>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, int _Dim2, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const tiled_extent<_Dim0, _Dim1, _Dim2>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, int _Dim1, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const tiled_extent<_Dim0, _Dim1>& _Compute_domain,
    const _Kernel_type& _Kernel);

template <int _Dim0, typename _Kernel_type>
void parallel_for_each(
    const accelerator_view& _Accl_view,
    const tiled_extent<_Dim0>& _Compute_domain,
    const _Kernel_type& _Kernel);
```

### <a name="parameters"></a>Параметры

*_Accl_view*<br/>
Объект `accelerator_view` для запуска параллельных вычислений.

*_Compute_domain*<br/>
Объект, `extent` содержащий данные для вычислений.

*_Dim0*<br/>
Размер `tiled_extent` объекта.

*_Dim1*<br/>
Размер `tiled_extent` объекта.

*_Dim2*<br/>
Размер `tiled_extent` объекта.

*_Kernel*<br/>
Ламбда или функциональный объект, который принимает\<аргумент типа "индекс _Rank>" и выполняет параллельные вычисления.

*_Kernel_type*<br/>
Лямбда или фанктор.

*_Rank*<br/>
Ранг степени.

## <a name="tile_static_memory_fence"></a><a name="tile_static_memory_fence"></a>tile_static_memory_fence

Блоки выполнения всех потоков в плитке до тех пор, пока все невыполненные `tile_static` доступы к памяти не будут завершены. Это гарантирует, `tile_static` что доступ к памяти будет виден другим потокам в плитке потока и выполняется в порядке программы.

```cpp
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Barrier*<br/>
Объект tile_barrier.

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
