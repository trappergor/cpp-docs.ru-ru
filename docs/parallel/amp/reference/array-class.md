---
title: "Класс Array | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array
- AMP/array
- AMP/Concurrency::array::array
- AMP/Concurrency::array::copy_to
- AMP/Concurrency::array::data
- AMP/Concurrency::array::get_accelerator_view
- AMP/Concurrency::array::get_associated_accelerator_view
- AMP/Concurrency::array::get_cpu_access_type
- AMP/Concurrency::array::get_extent
- AMP/Concurrency::array::reinterpret_as
- AMP/Concurrency::array::section
- AMP/Concurrency::array::view_as
- AMP/Concurrency::array::rank
- AMP/Concurrency::array::accelerator_view
- AMP/Concurrency::array::associated_accelerator_view
- AMP/Concurrency::array::cpu_access_type
- AMP/Concurrency::array::extent
dev_langs: C++
helpviewer_keywords: array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: "31"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad9e098ad485c7a96670c4249770b038333e1bc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="array-class"></a>Класс array
Представляет контейнер данных, используемый для перемещения данных в клавишей быстрого доступа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename value_type, int _Rank>  
friend class array;  
```  
  
#### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип элемента данных.  
  
 `_Rank`  
 Ранг массива.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор массива](#ctor)|Инициализирует новый экземпляр класса `array`.|  
|[~ array деструктор](#dtor)|Уничтожает `array` объекта.|  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[copy_to](#copy_to)|Копирует содержимое массива в другой массив.|  
|[data](#data)|Возвращает указатель на необработанные данные массива.|  
|[get_accelerator_view](#get_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , представляющий расположение, где выделяется массива. Это свойство может осуществляться только на ЦП.|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Возвращает второй [accelerator_view](accelerator-view-class.md) , передаваемый в качестве параметра при вызове промежуточной конструктор для создания экземпляра объекта `array` объекта.|  
|[get_cpu_access_type](#get_cpu_access_type)|Возвращает [access_type](concurrency-namespace-enums-amp.md#access_type) массива. Этот метод может осуществляться только на ЦП.|  
|[get_extent](#get_extent)|Возвращает [экстент](extent-class.md) объект массива.|  
|[reinterpret_as](#reinterpret_as)|Возвращает одномерный массив, который содержит все элементы в `array` объекта.|  
|[section](#section)|Возвращает подраздел `array` объект, находящийся в указанный источник и, возможно, который имеет указанную область.|  
|[view_as](#view_as)|Возвращает [array_view](array-view-class.md) , получаемый из `array` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор std::vector&lt;value_type&gt;](#operator_vec)|Использует `copy(*this, vector)` неявное преобразование массива в объект std::[вектор](../../../standard-library/vector-class.md) объекта.|  
|[Operator()](#operator_call)|Возвращает значение элемента, указанный параметрами.|  
|[оператор]](#operator_at)|Возвращает элемент, расположенный по указанному индексу.|  
|[operator=](#operator_eq)|Копирует содержимое указанного `array` объекта в другой.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Сохраняет ранг массива.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[accelerator_view](#accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , представляющий расположение, где выделяется массива. Это свойство может осуществляться только на ЦП.|  
|[associated_accelerator_view](#associated_accelerator_view)|Возвращает второй [accelerator_view](accelerator-view-class.md) , передаваемый в качестве параметра при вызове промежуточной конструктор для создания экземпляра объекта `array` объекта.|  
|[cpu_access_type](#cpu_access_type)|Возвращает [access_type](concurrency-namespace-enums-amp.md#access_type) , представляющий как доступ к хранилищу массива для ЦП.|  
|[extent](#extent)|Получает экстент, который определяет форму массива.|  
  
## <a name="remarks"></a>Примечания  
 Тип `array<T,N>` представляет высокую плотность и обычным (не ступенчатые) *N*-мерный массив, расположенных в определенном расположении ускоритель или ЦП. Тип данных элементов в массиве является `T`, который должен быть типа, совместимого с целевой сочетания клавиш. Несмотря на то что ранг, `N`, (из массива определяется статически и является частью типа, степени массива определяется средой выполнения и представляется с помощью класса `extent<N>`.  
  
 Массив может иметь любое количество измерений, хотя некоторые функциональные возможности, предназначенного для `array` объекты с одного ранга, второе и третье. Если опустить аргумент измерения, значение по умолчанию — 1.  
  
 Данные массива располагаются последовательно в памяти. Элементы, которые отличаются на единицу измерения младших являются смежными в памяти.  
  
 Массивы логически считаются типов значений, так как выполняется при копировании массива в другой массив глубокой копией. Два массива никогда не указывать на тех же данных.  
  
 `array<T,N>` Тип используется в различных сценариях:  
  
-   Как контейнер данных, который может использоваться в вычислениях с клавишей быстрого доступа.  
  
-   Как контейнер данных для хранения объема памяти на узле ЦП (который может использоваться для копирования в и из других массивов).  
  
-   Как промежуточный объект в качестве быстрого посредника в копиях устройство узла.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `array`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="dtor"></a>~ массива 

 Уничтожает `array` объекта.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="accelerator_view"></a>accelerator_view 

 Возвращает [accelerator_view](accelerator-view-class.md) , представляющий расположение, где выделяется массива. Это свойство может осуществляться только на ЦП.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="ctor"></a>Массив 

 Инициализирует новый экземпляр [класс array](array-class.md). Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы выполняются только в ЦП. Они не может выполняться на целевом Direct3D.  
  
```  
explicit array(  
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);  
  
explicit array(  
    int _E0) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first, 
    _InputIterator _Src_last) restrict(cpu);
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,    
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
explicit array(  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);  
  
array(  
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);  
  
array(const array& _Other) restrict(cpu);  
  
array(array&& _Other) restrict(cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Associated_Av`  
 Accelerator_view, который указывает местоположение предпочтительный объект массива.  
  
 `_Av`  
 [Accelerator_view](accelerator-view-class.md) объект, указывающий позицию массива.  
  
 `_Cpu_access_type`  
 Нужный [access_type](concurrency-namespace-enums-amp.md#access_type) для массива на ЦП. Этот параметр имеет значение по умолчанию `access_type_auto` оставляя ЦП `access_type` определение в среду выполнения. Фактический ЦП `access_type` для массива можно запрашивать с помощью `get_cpu_access_type` метод.  
  
 `_Extent`  
 Степень, в каждом измерении массива.  
  
 `_E0`  
 Наиболее значимые компонент экстента в этом разделе.  
  
 `_E1`  
 Далее к старший значащий компонент экстента в этом разделе.  
  
 `_E2`  
 Наименее значащие компонент экстента в этом разделе.  
  
 `_InputIterator`  
 Тип входного interator.  
  
 `_Src`  
 Объект для копирования.  
  
 `_Src_first`  
 Итератор с начала в контейнер источника.  
  
 `_Src_last`  
 Итератор конца в контейнер источника.  
  
 `_Other`  
 Другой источник данных.  
  
 `_Rank`  
 Ранг раздела.  
  
 `value_type`  
 Тип данных элементов, которые были скопированы.  
  
##  <a name="associated_accelerator_view"></a>associated_accelerator_view 

 Возвращает второй [accelerator_view](accelerator-view-class.md) , передаваемый в качестве параметра при вызове промежуточной конструктор для создания экземпляра объекта `array` объекта.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a>copy_to 

 Копирует содержимое `array` в другой `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 [Array_view](array-view-class.md) объект для копирования.  
  
##  <a name="cpu_access_type"></a>cpu_access_type 

 Возвращает access_type ЦП, допустимое для данного массива.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="data"></a>данные 

 Возвращает указатель на необработанные данные `array`.  
  
```  
value_type* data() restrict(amp, cpu);
  
const value_type* data() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные массива.  
  
##  <a name="extent"></a>экстент 

 Возвращает [экстент](extent-class.md) объект, который определяет форму `array`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="get_accelerator_view"></a>get_accelerator_view 

 Возвращает [accelerator_view](accelerator-view-class.md) объект, представляющий расположение где `array` выделена память для объекта. Это свойство может осуществляться только на ЦП.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;  
```    
  
### <a name="return-value"></a>Возвращаемое значение  
 `accelerator_view` Объект, представляющий расположение где `array` выделена память для объекта.  
  
##  <a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 Возвращает второй [accelerator_view](accelerator-view-class.md) , передаваемый в качестве параметра при вызове промежуточной конструктор для создания экземпляра объекта `array` объекта.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Второй [accelerator_view](accelerator-view-class.md) объект, переданный в конструктор промежуточной.  
  
##  <a name="get_cpu_access_type"></a>get_cpu_access_type 

 Возвращает access_type ЦП, что разрешено для данного массива.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="get_extent"></a>get_extent 

 Возвращает [экстент](extent-class.md) объекта `array`.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `extent` Объекта `array`.  
  
##  <a name="operator_vec"></a>оператор std::vector&lt;value_type&gt; 

 Использует `copy(*this, vector)` неявное преобразование массива в объект std::vector.  
  
```  
operator std::vector<value_type>() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип данных элементов вектора.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект типа `vector<T>` , содержащий копию данных, содержащихся в массиве.  
  
##  <a name="operator_call"></a>Operator() 

 Возвращает значение элемента, указанный параметрами.  
  
```  
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);
  
value_type& operator() (int _I0, int _I1) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;
  
value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Расположение элемента.  
  
 `_I0`  
 Наиболее значимые компонент источника в этом разделе.  
  
 `_I1`  
 Далее к старший значащий компонент источника в этом разделе.  
  
 `_I2`  
 Наименее значащие компонент источника в этом разделе.  
  
 `_I`  
 Расположение элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, указанный параметрами.  
  
##  <a name="operator_at"></a>оператор] 

 Возвращает элемент, расположенный по указанному индексу.  
  
```  
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator[]  
    (const index<_Rank>& _Index) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```  
    
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс.  
  
 `_I`  
 Индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент, расположенный по указанному индексу.  
  
##  <a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного `array` объекта.  
  
```  
array& operator= (const array& _Other) restrict(cpu);  
   
array& operator= (array&& _Other) restrict(cpu);  
 
array& operator= (  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `array` Объект для копирования из.  
  
 `_Src`  
 `array` Объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `array` объекта.  
  
##  <a name="rank"></a>Ранг 

 Сохраняет ранг объекта `array`.  
  
```  
static const int rank = _Rank;  
```  
## <a name="reinterpret_as"></a>reinterpret_as 

Повторно интерпретирует к массиву по одномерный array_view, который при необходимости может иметь тип отличается от исходного массива.

### <a name="syntax"></a>Синтаксис
``` 
template <typename _Value_type2>  
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);  
  
template <typename _Value_type2>  
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);  
``` 
  
### <a name="parameters"></a>Параметры  
`_Value_type2`Тип данных, возвращаемых данных.

### <a name="return-value"></a>Возвращаемое значение
Array_view или константный объект array_view, который основан на массиве, с типом элемента интерпретировать из T ElementType и ранг сократить от N до 1.

### <a name="remarks"></a>Примечания
Иногда бывает удобно для просмотра многомерного массива, как будто оно является линейной одномерный массив, возможно, с типом отличается от исходного массива. Этот метод можно использовать с этой целью.
**Внимание** повторной интерпретации объект массива, используя другое значение тип является потенциально небезопасные операции. Рекомендуется тщательно применения этих функциональных возможностей. 

Ниже приведен пример кода.

```cpp  
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...; 
array_view<float,1> v = a.reinterpret_as<float>(); 

assert(v.extent == 3*a.extent);
```  
  
##  <a name="section"></a>раздел 

 Возвращает подраздел `array` объект, находящийся в указанный источник и, возможно, который имеет указанную область.  
  
```  
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);
  
array_view<value_type,1> section(
    int _I0,  
    int _E0) restrict(amp,cpu);
  
array_view<const value_type,1> section(
    int _I0,  
    int _E0) const restrict(amp,cpu);
  
array_view<value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) restrict(amp,cpu);
  
array_view<const value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);
  
array_view<value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) restrict(amp,cpu);
  
array_view<const value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_E0`  
 Наиболее значимые компонент экстента в этом разделе.  
  
 `_E1`  
 Далее к старший значащий компонент экстента в этом разделе.  
  
 `_E2`  
 Наименее значащие компонент экстента в этом разделе.  
  
 `_Ext`  
 [Экстент](extent-class.md) объекта, который задает область, в разделе. Источником является 0.  
  
 `_Idx`  
 [Индекс](index-class.md) объект, который указывает расположение начала координат. Подраздел является rest экстента.  
  
 `_I0`  
 Наиболее значимые компонент источника в этом разделе.  
  
 `_I1`  
 Далее к старший значащий компонент источника в этом разделе.  
  
 `_I2`  
 Наименее значащие компонент источника в этом разделе.  
  
 `_Rank`  
 Ранг раздела.  
  
 `_Section_extent`  
 [Экстент](extent-class.md) объекта, который задает область, в разделе.  
  
 `_Section_origin`  
 [Индекс](index-class.md) объект, который указывает расположение начала координат.  
  
 `value_type`  
 Тип данных элементов, которые были скопированы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает подраздел `array` объект, находящийся в указанный источник и, возможно, который имеет указанную область. Только если `index` объект указан, подраздел содержит все элементы в сетке связанные, имеют индексы, размер которых превышает индексы элементов в `index` объекта.  
  
##  <a name="view_as"></a>view_as 

 Повторно интерпретирует этот массив в виде [array_view](array-view-class.md) другого ранга.  
  
```  
template <int _New_rank>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

 
template <int _New_rank>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_New_rank`  
 Ранг `extent` объекта, переданного в качестве параметра.  
  
 `_View_extent`  
 Экстент, который используется для создания нового [array_view](array-view-class.md) объекта.  
  
 `value_type`  
 Тип данных элементов в исходные `array` объекта и возвращаемый `array_view` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 [Array_view](array-view-class.md) , получаемый.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
