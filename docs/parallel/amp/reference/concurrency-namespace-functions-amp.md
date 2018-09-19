---
title: Функции пространства имен Concurrency (AMP) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba253744b7abc3cc37dfa765ebe15af49b89c0ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069148"
---
# <a name="concurrency-namespace-functions-amp"></a>Функции пространства имен Concurrency (AMP)
||||  
|-|-|-|  
|[all_memory_fence](#all_memory_fence)|[amp_uninitialize](#amp_uninitialize)|[atomic_compare_exchange](#atomic_compare_exchange)|  
|[atomic_exchange функции (C++ AMP)](#atomic_exchange)|[atomic_fetch_add функции (C++ AMP)](#atomic_fetch_add)|[atomic_fetch_and функции (C++ AMP)](#atomic_fetch_and)|  
|[atomic_fetch_dec](#atomic_fetch_dec)|[atomic_fetch_inc](#atomic_fetch_inc)|[atomic_fetch_max](#atomic_fetch_max)|  
|[atomic_fetch_min](#atomic_fetch_min)|[atomic_fetch_or функции (C++ AMP)](#atomic_fetch_or)|[atomic_fetch_sub функции (C++ AMP)](#atomic_fetch_sub)|  
|[atomic_fetch_xor функции (C++ AMP)](#atomic_fetch_xor)|[copy](#copy)|[copy_async](#copy_async)|  
|[direct3d_abort](#direct3d_abort)|[direct3d_errorf](#direct3d_errorf)|[direct3d_printf](#direct3d_printf)|  
|[global_memory_fence](#global_memory_fence)|[parallel_for_each функции (C++ AMP)](#parallel_for_each)|[tile_static_memory_fence](#tile_static_memory_fence)|  
  
##  <a name="all_memory_fence"></a>  all_memory_fence  
 Блокирует выполнение всех потоков в плитке, пока не будут завершены все доступы к памяти. Это гарантирует, что все доступы к памяти видимы для других потоков в плитке потоков и выполняются в программном порядке.  
  
```  
inline void all_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Barrier*<br/>
Объект `tile_barrier`.  
  
##  <a name="amp_uninitialize"></a>  amp_uninitialize  
 Отменяет инициализацию среды выполнения C++ AMP. Допустимо вызывать эту функцию несколько раз во время существования приложения. Вызов любого C++ AMP API после вызова этой функции будет заново инициализирована, среда выполнения C++ AMP. Обратите внимание, что не допускается использовать объекты C++ AMP между вызовами этой функции, и это приведет к неопределенному поведению. Кроме того одновременно вызывать эту функцию и других интерфейсов API AMP недопустимо и приведет к неопределенному поведению.  
  
```  
void __cdecl amp_uninitialize();
```  
  
##  <a name="atomic_compare_exchange"></a>  atomic_compare_exchange  
 Атомарным образом сравнивает значение, хранящееся в памяти, заданные в первом аргументе на предмет равенства со значением второго заданного аргумента, и если значения совпадают, значение в области памяти меняется на что третьего заданного аргумента.  
  
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
*_Dest*<br/>
Расположение, из которых используется один из сравниваемых значений считывается, и к которому новое значение, если таковые имеются, будет храниться.  
  
*_Expected_value*<br/>
Расположение, из которого считываются второе значение для сравнения.  
  
*значение*<br/>
Значение для сохранения в область памяти, заданные в `_Dest` Если `_Dest` равен `_Expected_value`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если операция выполнена успешно; в противном случае — значение `false`.  
  

##  <a name="atomic_exchange"></a>  atomic_exchange функции (C++ AMP)  
 Задает значение целевого расположения в виде атомарной операции.  
  
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
*_Dest*<br/>
Указатель на расположение адрес назначения.  
  
*значение*<br/>
Новое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение для нового местонахождения.  
  

##  <a name="atomic_fetch_add"></a>  atomic_fetch_add функции (C++ AMP)  
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
*_Dest*<br/>
Указатель на область памяти.  
  
*значение*<br/>
Добавляемое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_and"></a>  atomic_fetch_and функции (C++ AMP)  
 Атомарным образом выполняет побитовую операцию и значение и значение ячейки памяти.  
  
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
*_Dest*<br/>
Указатель на область памяти.  
  
*значение*<br/>
Значение, используемое в побитовое и вычисления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_dec"></a>  atomic_fetch_dec  
 Атомарным образом уменьшает значение, сохраненное в указанной области памяти.  
  
```  
inline int atomic_fetch_dec(_Inout_ int* _Dest  
    ) restrict(amp)

 
inline unsigned int atomic_fetch_dec(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Dest*<br/>
Расположение в памяти уменьшаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, хранящееся в памяти.  
  
##  <a name="atomic_fetch_inc"></a>  atomic_fetch_inc  
 Атомарным образом увеличивает значение, хранящееся в указанной области памяти.  
  
```  
inline int atomic_fetch_inc(_Inout_ int* _Dest) restrict(amp);

 
inline unsigned int atomic_fetch_inc(_Inout_ unsigned int* _Dest) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Dest*<br/>
Расположение в памяти для увеличения значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, хранящееся в памяти.  
  
##  <a name="atomic_fetch_max"></a>  atomic_fetch_max  
 Атомарным образом вычисляет максимальное значение между значением, хранящимся в области памяти, указанный в первом аргументе и значение, указанное во втором аргументе и сохраняет его в той же области памяти.  
  
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
*_Dest*<br/>
Расположение, из которых используется один из сравниваемых значений считывается, и к которой будет храниться максимальное из двух значений.  
  
*значение*<br/>
Значение для сравнения со значением в указанном расположении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, сохраненное в расположении, указанном расположении.  
  
##  <a name="atomic_fetch_min"></a>  atomic_fetch_min  
 Атомарным образом вычисляет минимальное значение между значением, хранящимся в области памяти, указанный в первом аргументе и значение, указанное во втором аргументе и сохраняет его в той же области памяти.  
  
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
*_Dest*<br/>
Расположение, из которых используется один из сравниваемых значений считывается, и к которой будет храниться минимальное из двух значений.  
  
*значение*<br/>
Значение для сравнения со значением в указанном расположении.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение, сохраненное в расположении, указанном расположении.  
  
##  <a name="atomic_fetch_or"></a>  atomic_fetch_or функции (C++ AMP)  
 Атомарным образом выполняет побитовую операцию или со значением и значением области памяти.  
  
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
*_Dest*<br/>
Указатель на область памяти.  
  
*значение*<br/>
Значение для использования в расчете побитового OR.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_sub"></a>  atomic_fetch_sub функции (C++ AMP)  
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
*_Dest*<br/>
Указатель на расположение адрес назначения.  
  
*значение*<br/>
Значение для вычитания.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="atomic_fetch_xor"></a>  atomic_fetch_xor функции (C++ AMP)  
 Атомарным образом WordRight действует побитовой операции XOR значение и расположение в памяти.  
  
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
*_Dest*<br/>
Указатель на область памяти.  
  
*значение*<br/>
Значение, используемое в вычислении исключающего логического Сложения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Исходное значение ячейки памяти.  
  
##  <a name="copy"></a>  copy  
 Копирует объект C++ AMP. Выполнены все требования синхронной передачи данных. Не удается скопировать данные, при выполнении кода на ускорителе. Эта функция выглядит `copy(src, dest)`.  
  
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
*_Dest*<br/>
Объект для копирования.  
  
*_DestIter*<br/>
Выходной итератор на начальную позицию в месте назначения.  
  
*InputIterator*<br/>
Тип итератора ввода.  
  
*OutputIterator*<br/>
Тип итератора вывода.  
  
*_Rank*<br/>
Ранг объекта для копирования из или объект для копирования.  
  
*_Src*<br/>
Объект, который требуется скопировать.  
  
*_SrcFirst*<br/>
Итератор с начала в исходном контейнере.  
  
*_SrcLast*<br/>
Итератор конца в исходном контейнере.  
  
*value_type*<br/>
Тип данных элементов, которые будут скопированы.  
  
##  <a name="copy_async"></a>  copy_async  
 Копирует объект C++ AMP и возвращает [completion_future](completion-future-class.md) объект, который можно использовать для ожидания. Не удается скопировать данные, при выполнении кода на ускорителе.  Эта функция выглядит `copy(src, dest)`.  
  
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
*_Dest*<br/>
Объект для копирования.  
  
*_DestIter*<br/>
Выходной итератор на начальную позицию в месте назначения.  
  
*InputIterator*<br/>
Тип итератора ввода.  
  
*OutputIterator*<br/>
Тип итератора вывода.  
  
*_Rank*<br/>
Ранг объекта для копирования из или объект для копирования.  
  
*_Src*<br/>
Объект, который требуется скопировать.  
  
*_SrcFirst*<br/>
Итератор с начала в исходном контейнере.  
  
*_SrcLast*<br/>
Итератор конца в исходном контейнере.  
  
*value_type*<br/>
Тип данных элементов, которые будут скопированы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `future<void>` , можно использовать для ожидания.  
  
##  <a name="direct3d_abort"></a>  direct3d_abort  
 Прерывает выполнение функции с предложением ограничения `restrict(amp)` . Когда среда выполнения AMP обнаруживает вызов, он вызывает [runtime_exception](runtime-exception-class.md) исключение с сообщением об ошибке «программной прорисовки: инструкция прекращения работы шейдера».  
  
```  
void direct3d_abort() restrict(amp);
```  
  
##  <a name="direct3d_errorf"></a>  direct3d_errorf  
 Выводит отформатированную строку в окне вывода Visual Studio. Он вызывается из функции с помощью `restrict(amp)` предложение ограничения. Когда среда выполнения AMP обнаруживает вызов, он вызывает [runtime_exception](runtime-exception-class.md) исключение с этой же строкой форматирования.  
  
```  
void direct3d_errorf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="direct3d_printf"></a>  direct3d_printf  
 Выводит отформатированную строку в окне вывода Visual Studio. Он вызывается из функции с помощью `restrict(amp)` предложение ограничения.  
  
```  
void direct3d_printf(
    const char *,  
 ...) restrict(amp);
```  
  
##  <a name="global_memory_fence"></a>  global_memory_fence  
 Блокирует выполнение всех потоков в плитке до всех глобального доступа к памяти будет завершена. Это гарантирует, что доступы к памяти видимы для других потоков в плитке потоков и выполняются в программном порядке.  
  
```  
inline void global_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Barrier*<br/>
Объект tile_barrier  
  
##  <a name="parallel_for_each"></a>  parallel_for_each функции (C++ AMP)  
 Выполняет функцию в вычислительном домене. Дополнительные сведения см. в разделе [Обзор C++ AMP](../../../parallel/amp/cpp-amp-overview.md).  
  
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
*_Accl_view*<br/>
`accelerator_view` Выполнения параллельных вычислений объекта.  
  
*_Compute_domain*<br/>
`extent` Объект, содержащий данные для вычисления.  
  
*_Dim0*<br/>
Измерение объекта `tiled_extent` объекта.  
  
*_Dim1*<br/>
Измерение объекта `tiled_extent` объекта.  
  
*_Dim2*<br/>
Измерение объекта `tiled_extent` объекта.  
  
*_Kernel*<br/>
Объект лямбда или функции, который принимает аргумент типа «индекс\<_Rank >» и выполняет параллельное вычисление.  
  
*_Kernel_type*<br/>
Лямбда-выражение или функтор.  
  
*_Rank*<br/>
Ранг области памяти.  
  
##  <a name="tile_static_memory_fence"></a>  tile_static_memory_fence  
 Блокирует выполнение всех потоков в плитке, пока все необработанные `tile_static` будет завершено обращение к памяти. Это гарантирует, что `tile_static` обращений к памяти видимы для других потоков в плитке потоков и доступы осуществляются в программном порядке.  
  
```  
inline void tile_static_memory_fence(const tile_barrier& _Barrier) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
*_Barrier*<br/>
Объект tile_barrier.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
