---
title: "Функции пространство имен Concurrency (AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
ms.assetid: 2bef0985-cb90-4ece-90b9-66529aec73c9
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: a976cc06b49b10d5bb8dcecb10e114efdd89faa8
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-functions-amp"></a>Функции пространство имен Concurrency (AMP)
||||  
|-|-|-|  
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|  
|[Функция atomic_exchange (C++ AMP)](#atomic_exchange)|[Функция atomic_fetch_add (C++ AMP)](#atomic_fetch_add)|[Функция atomic_fetch_and (C++ AMP)](#atomic_fetch_and)|  
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|  
|[atomic_fetch_min](#atomic_fetch_min)|[Функция atomic_fetch_or (C++ AMP)](#atomic_fetch_or)|[Функция atomic_fetch_sub (C++ AMP)](#atomic_fetch_sub)|  
|[Функция atomic_fetch_xor (C++ AMP)](#atomic_fetch_xor)|[copy](#copy)|[copy_async](#copy_async)|  
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|  
|[global_memory_fence](#global_memory_fence)|[Функция parallel_for_each (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|  
  
##  <a name="all_memory_fence"></a>all_memory_fence  
 Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к памяти. Это гарантирует, что все обращения к памяти являются видимыми для других потоков в мозаике потоков и выполняются в порядке программы.  
  
```  
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Barrier`  
 Объект `tile_barrier`.  
  
##  <a name="amp_uninitialize"></a>amp_uninitialize  
 Отменяет инициализацию среды выполнения C++ AMP. Эта функция вызывается несколько раз за время существования приложения допустимо. Вызов любого afer C++ AMP API, вызов этой функции будет повторная инициализация среды выполнения C++ AMP. Обратите внимание, что не допускается использование объектов C++ AMP через вызовы этой функции, и это приведет к неопределенному поведению. Кроме того одновременно вызов этой функции и другие интерфейсы API AMP недопустим и приведет к неопределенному поведению.  
  
```  
void __cdecl amp_uninitialize();
```  
  
##  <a name="atomic_compare_exchange"></a>atomic_compare_exchange  
 Атомарным образом сравнивает значение, хранящееся в памяти в первый аргумент на равенство со значением второго заданного аргумента, и если значения совпадают, в область памяти изменяется значение для третьего задан аргумент.  
  
```  
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
 `_Dest`  
 Расположение, из которых используется один из сравниваемых значений считывается и к которому новое значение, если таковые имеются, будет храниться.  
  
 `_Expected_value`  
 Расположение, из которого считываются второе значение для сравнения.  
  
 `value`  
 Значение хранится в расположении памяти, заданный в `_Dest` Если `_Dest` равен `_Expected_value`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если операция выполнена успешно; в противном случае — значение `false`.  
  

##  <a name="atomic_exchange"></a>Функция atomic_exchange (C++ AMP)  
 Задает значение место назначения в виде атомарной операции.  
  
```  
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
 `_Dest`  
 Указатель на расположение целевой.  
  
 `value`  
 Новое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение целевого расположения.  
  

##  <a name="atomic_fetch_add"></a>Функция atomic_fetch_add (C++ AMP)  
 Атомарным образом добавьте значение к значению ячейки памяти.  
  
```  
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
 `_Dest`  
 Указатель на область памяти.  
  
 `value`  
 Добавляемое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_and"></a>Функция atomic_fetch_and (C++ AMP)  
 Единым блоком выполняет побитовую операцию и значение и значение ячейки памяти.  
  
```  
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
 `_Dest`  
 Указатель на область памяти.  
  
 `value`  
 Значение, используемое в вычислении побитовое и.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_dec"></a>atomic_fetch_dec  
 Атомарным образом уменьшает значение, хранящееся в заданном расположении памяти.  
  
```  
inline int atomic_fetch_dec(_Inout_ int* _Dest  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Расположение в памяти для уменьшения значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, хранящееся в расположение в памяти.  
  
##  <a name="atomic_fetch_inc"></a>atomic_fetch_inc  
 Атомарным образом увеличивает значение, хранящееся в заданном расположении памяти.  
  
```  
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

 
inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Расположение в памяти для увеличения значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, хранящееся в расположение в памяти.  
  
##  <a name="atomic_fetch_max"></a>atomic_fetch_max  
 Автоматически вычисляет максимальное значение между значением, хранящимся в памяти расположении, указанном в первого аргумента и значения, указанного в качестве второго аргумента и сохраняет его в том же расположении памяти.  
  
```  
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
 `_Dest`  
 Чтение расположение, из которых используется один из сравниваемых значений, и к которым будет храниться более двух значений.  
  
 `value`  
 Значение, которое будет сравниваться со значением в указанном месте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, хранящиеся в указанном расположении расположении.  
  
##  <a name="atomic_fetch_min"></a>atomic_fetch_min  
 Автоматически вычисляет минимальное значение между значением, хранящимся в памяти расположении, указанном в первого аргумента и значения, указанного в качестве второго аргумента и сохраняет его в том же расположении памяти.  
  
```  
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
 `_Dest`  
 Чтение расположение, из которых используется один из сравниваемых значений, и к которым будет храниться минимальное из двух значений.  
  
 `value`  
 Значение, которое будет сравниваться со значением в указанном месте.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, хранящиеся в указанном расположении расположении.  
  
##  <a name="atomic_fetch_or"></a>Функция atomic_fetch_or (C++ AMP)  
 Единым блоком выполняет операцию побитового или со значением и значение ячейки памяти.  
  
```  
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
 `_Dest`  
 Указатель на область памяти.  
  
 `value`  
 Значение, используемое в вычислении побитового OR.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_sub"></a>Функция atomic_fetch_sub (C++ AMP)  
 Атомарным образом вычитает значение из ячейки памяти.  
  
```  
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
 `_Dest`  
 Указатель на расположение целевой.  
  
 `value`  
 Значение, которое будет вычтен.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_xor"></a>Функция atomic_fetch_xor (C++ AMP)  
 Атомарным образом WordRight действует операции побитового исключающего или значения и расположение в памяти.  
  
```  
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
 `_Dest`  
 Указатель на область памяти.  
  
 `value`  
 Значение, используемое в вычислении XOR.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="copy"></a>  copy  
 Копирует объект C++ AMP. Все синхронные данные передачи требований. Не удается скопировать данные при выполнении кода в ускорителя. Эта функция выглядит `copy(src, dest)`.  
  
```  
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
 `_Dest`  
 Объект для копирования.  
  
 `_DestIter`  
 Итератор вывода начальное положение в месте назначения.  
  
 `InputIterator`  
 Тип ввода interator.  
  
 `OutputIterator`  
 Тип итератора вывода.  
  
 `_Rank`  
 Ранг, копируемых из объекта или объекта для копирования.  
  
 `_Src`  
 Объект для копирования.  
  
 `_SrcFirst`  
 Итератор начало в контейнер источника.  
  
 `_SrcLast`  
 Итератор конца в контейнер источника.  
  
 `value_type`  
 Тип данных элементов, которые будут скопированы.  
  
##  <a name="copy_async"></a>copy_async  
 Копирует объект C++ AMP и возвращает [completion_future](completion-future-class.md) объект, который может быть ожидаемым. Не удается скопировать данные при выполнении кода в ускорителя.  Эта функция выглядит `copy(src, dest)`.  
  
```  
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
 `_Dest`  
 Объект для копирования.  
  
 `_DestIter`  
 Итератор вывода начальное положение в месте назначения.  
  
 `InputIterator`  
 Тип ввода interator.  
  
 `OutputIterator`  
 Тип итератора вывода.  
  
 `_Rank`  
 Ранг, копируемых из объекта или объекта для копирования.  
  
 `_Src`  
 Объект для копирования.  
  
 `_SrcFirst`  
 Итератор начало в контейнер источника.  
  
 `_SrcLast`  
 Итератор конца в контейнер источника.  
  
 `value_type`  
 Тип данных элементов, которые будут скопированы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `future<void>` , можно ожидать.  
  
##  <a name="direct3d_abort"></a>direct3d_abort  
 Прерывает выполнение функции с предложением ограничения `restrict(amp)` . Когда AMP среда выполнения обнаруживает вызов, он выдает [runtime_exception](runtime-exception-class.md) исключение появляется сообщение об ошибке «прорисовки: шейдера прервать попадание в инструкции».  
  
```  
void direct3d_abort() restrict(amp);
```  
  
##  <a name="direct3d_errorf"></a>direct3d_errorf  
 Выводит форматированную строку в окне вывода Visual Studio. Он вызывается из функции с `restrict(amp)` предложения ограничения. Когда среда выполнения AMP обнаруживает вызов, он выдает [runtime_exception](runtime-exception-class.md) исключение с ту же строку форматирования.  
  
```  
void direct3d_errorf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="direct3d_printf"></a>direct3d_printf  
 Выводит форматированную строку в окне вывода Visual Studio. Он вызывается из функции с `restrict(amp)` предложения ограничения.  
  
```  
void direct3d_printf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="global_memory_fence"></a>global_memory_fence  
 Блокирует выполнение всех потоков в мозаике до обращения к памяти все глобальные завершена. Это гарантирует, что доступ к глобальной памяти являются видимыми для других потоков в мозаике потоков и выполняются в порядке программы.  
  
```  
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Barrier`  
 Объект tile_barrier  
  
##  <a name="parallel_for_each"></a>Функция parallel_for_each (C++ AMP)  
 Выполняет функцию домене вычислений. Дополнительные сведения см. в разделе [Обзор C++ AMP](../../../parallel/amp/cpp-amp-overview.md).  
  
```  
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
 `_Accl_view`  
 `accelerator_view` Выполнять параллельные вычисления объект.  
  
 `_Compute_domain`  
 `extent` Объект, содержащий данные для вычисления.  
  
 `_Dim0`  
 Измерения `tiled_extent` объекта.  
  
 `_Dim1`  
 Измерения `tiled_extent` объекта.  
  
 `_Dim2`  
 Измерения `tiled_extent` объекта.  
  
 `_Kernel`  
 Лямбда-выражение или функция объекта, который принимает аргумент типа «индекс\<_Rank настроек» и выполняет параллельные вычисления.  
  
 `_Kernel_type`  
 Лямбда-выражение или функтор.  
  
 `_Rank`  
 Ранг экстента.  
  
##  <a name="tile_static_memory_fence"></a>tile_static_memory_fence  
 Блокирует выполнение всех потоков в мозаике, пока все необработанные `tile_static` завершили доступов к памяти. Это гарантирует, что `tile_static` доступов к памяти являются видимыми для других потоков в мозаике потоков и обращается к выполняются в порядке программы.  
  
```  
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Barrier`  
 Объект tile_barrier.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

