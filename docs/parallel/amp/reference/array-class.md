---
title: "Класс array | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array - класс"
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# Класс array
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет контейнер данных, используемый для перемещения данных в ускорителя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
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
|[Конструктор Array::Array](#array__array_constructor)|Инициализирует новый экземпляр класса `array`.|  
|[Массив:: ~ array деструктор](#array___dtorarray_destructor)|Уничтожает `array` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Array::copy_to](#array__copy_to_method)|Копирует содержимое массива в другой массив.|  
|[Метод Array::Data](#array__data_method)|Возвращает указатель на необработанные данные массива.|  
|[Метод Array::get_accelerator_view](#array__get_accelerator_view_method)|Возвращает [accelerator_view](../Topic/accelerator_view%20Class.md) представляющий расположение, где выделяется массива. Это свойство может осуществляться только на ЦП.|  
|[Метод Array::get_associated_accelerator_view](#array__get_associated_accelerator_view_method)|Возвращает второй [accelerator_view](../Topic/accelerator_view%20Class.md) объект, который передается в качестве параметра при вызове промежуточной конструктор для создания экземпляра [массива](../../../parallel/amp/reference/array-class.md) объекта.|  
|[Метод Array::get_cpu_access_type](#array__get_cpu_access_type_method)|Возвращает [access_type](access_type%20Enumeration.md) массива. Этот метод может осуществляться только на ЦП.|  
|[Метод Array::get_extent](#array__get_extent_method)|Возвращает [область](../Topic/extent%20Class%20\(C++%20AMP\).md) объект массива.|  
|[Метод Array::reinterpret_as](#array__reinterpret_as_method)|Возвращает одномерный массив, содержащий все элементы в `array` объекта.|  
|[Метод Array::Section](#array__section_method)|Возвращает подраздел [массива](../../../parallel/amp/reference/array-class.md) объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область.|  
|[Метод Array::view_as](#array__view_as_method)|Возвращает [array_view](../../../parallel/amp/reference/array-view-class.md) получаемый из `array` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Array::operator std::vector&lt;value_type&gt; оператор](#array__operator_std__vector_lt__value_type_gt__operator)|Использует `copy(*this, vector)` неявно Преобразуемый массив std::[вектор](vector%20Class.md) объекта.|  
|[Оператор Array:: operator()](#array__operator___operator)|Возвращает значение элемента, определяются параметрами.|  
|[Оператор Array::operator]](#array__operator_at_operator)|Возвращает элемент, который находится по указанному индексу.|  
|[Array::operator =-оператор](#array__operator_eq_operator)|Копирует содержимое указанного `array` объекта в другой.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа Array::Rank](#array__rank_constant)|Сохраняет ранг массива.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[элемент данных Array::accelerator_view](#array__accelerator_view_data_member)|Возвращает [accelerator_view](../Topic/accelerator_view%20Class.md) представляющий расположение, где выделяется массива. Это свойство может осуществляться только на ЦП.|  
|[элемент данных Array::associated_accelerator_view](#array__associated_accelerator_view_data_member)|Возвращает второй [accelerator_view](../Topic/accelerator_view%20Class.md) объект, который передается в качестве параметра при вызове промежуточной конструктор для создания экземпляра [массива](../../../parallel/amp/reference/array-class.md) объекта.|  
|[элемент данных Array::cpu_access_type](#array__cpu_access_type_data_member)|Возвращает [access_type](access_type%20Enumeration.md) представляющий доступ ЦП хранилища массива.|  
|[элемент данных Array::Extent](#array__extent_data_member)|Получает экстент, который определяет форму массива.|  
  
## <a name="remarks"></a>Примечания  
 Тип `array<T,N>` представляет плотным и обычным (не ступенчатые) *N*-мерный массив, расположенный в определенном расположении, например ускоритель или ЦП. Тип данных элементов в массиве является `T`, который должен быть типа, совместимого с ускорителем целевой. Несмотря на то что ранг, `N`, (из массива определяется статически и часть типа, степени массива определяется средой выполнения и выражается с помощью класса `extent<N>`.  
  
 Массив может иметь любое количество измерений, хотя некоторые функциональные возможности, предназначенного для `array` объектов с rank один, два и три. Если опустить аргумент измерения, значение по умолчанию — 1.  
  
 Массив данных располагаются последовательно в памяти. Элементы, которые отличаются на единицу измерения младших смежных участках памяти.  
  
 Массивы логически считаются типов значений, так как выполняется при копировании массива в другой массив глубокую копию. Два массива никогда не указывать на тех же данных.  
  
  `array<T,N>` Тип используется в нескольких сценариях:  
  
-   В качестве контейнера данных, можно использовать в вычислениях с ускорителя.  
  
-   В качестве контейнера данных для хранения в памяти ЦП узла (который может использоваться для копирования в и из других массивов).  
  
-   Как промежуточный объект в качестве быстро посредника в копии узла для устройства.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `array`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="a-namearraydtorarraydestructora-arrayarray-destructor"></a><a name="array___dtorarray_destructor"></a>  Массив:: ~ array деструктор  
 Уничтожает `array` объекта.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="a-namearrayacceleratorviewdatamembera-arrayacceleratorview-data-member"></a><a name="array__accelerator_view_data_member"></a>  элемент данных Array::accelerator_view  
 Возвращает [accelerator_view](../Topic/accelerator_view%20Class.md) представляющий расположение, где выделяется массива. Это свойство может осуществляться только на ЦП.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="a-namearrayarrayconstructora-arrayarray-constructor"></a><a name="array__array_constructor"></a>  Конструктор Array::Array  
 Инициализирует новый экземпляр [класс array](../../../parallel/amp/reference/array-class.md). Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы выполняются только в ЦП. Они не может выполняться на целевом Direct3D.  
  
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

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
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

 
array(
    const array& _Other) restrict(cpu);

 
array(
    array&& _Other) restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Associated_Av`  
 Accelerator_view, который указывает местоположение Предпочитаемая массива.  
  
 `_Av`  
  [Accelerator_view](../Topic/accelerator_view%20Class.md) объект, указывающий расположение в массиве.  
  
 `_Cpu_access_type`  
 Требуемый [access_type](access_type%20Enumeration.md)  для массива на ЦП. Этот параметр имеет значение по умолчанию `access_type_auto` оставляя ЦП `access_type` Определение в среду выполнения. Фактический ЦП `access_type` для массива можно запрашивать с помощью `get_cpu_access_type` метод.  
  
 `_Extent`  
 Область, в каждом измерении массива.  
  
 `_E0`  
 Наиболее значимые компонент экстента в этом разделе.  
  
 `_E1`  
 Далее к значащий компонент экстента в этом разделе.  
  
 `_E2`  
 Компонент младших экстента в этом разделе.  
  
 `_InputIterator`  
 Тип ввода interator.  
  
 `_Src`  
 Объект для копирования.  
  
 `_Src_first`  
 Итератор начало в контейнер источника.  
  
 `_Src_last`  
 Итератор конца в контейнер источника.  
  
 `_Other`  
 Другой источник данных.  
  
 `_Rank`  
 Ранг раздела.  
  
 `value_type`  
 Тип данных элементов, которые будут скопированы.  
  
##  <a name="a-namearrayassociatedacceleratorviewdatamembera-arrayassociatedacceleratorview-data-member"></a><a name="array__associated_accelerator_view_data_member"></a>  элемент данных Array::associated_accelerator_view  
 Возвращает второй [accelerator_view](../Topic/accelerator_view%20Class.md) объект, который передается в качестве параметра при вызове промежуточной конструктор для создания экземпляра [массива](../../../parallel/amp/reference/array-class.md) объекта.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namearraycopytomethoda-arraycopyto-method"></a><a name="array__copy_to_method"></a>  Метод Array::copy_to  
 Копирует содержимое [массива](../../../parallel/amp/reference/array-class.md) в другой `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
  [Array_view](../../../parallel/amp/reference/array-view-class.md) объект для копирования.  
  
##  <a name="a-namearraycpuaccesstypedatamembera-arraycpuaccesstype-data-member"></a><a name="array__cpu_access_type_data_member"></a>  элемент данных Array::cpu_access_type  
 Возвращает access_type ЦП, допустимое для данного массива.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="a-namearraydatamethoda-arraydata-method"></a><a name="array__data_method"></a>  Метод Array::Data  
 Возвращает указатель на необработанные данные [массива](../../../parallel/amp/reference/array-class.md).  
  
```  
value_type* data() restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные массива.  
  
##  <a name="a-namearrayextentdatamembera-arrayextent-data-member"></a><a name="array__extent_data_member"></a>  элемент данных Array::Extent  
 Возвращает [область](../Topic/extent%20Class%20\(C++%20AMP\).md) объект, который определяет форму [массива](../../../parallel/amp/reference/array-class.md).  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearraygetacceleratorviewmethoda-arraygetacceleratorview-method"></a><a name="array__get_accelerator_view_method"></a>  Метод Array::get_accelerator_view  
 Возвращает [accelerator_view](../Topic/accelerator_view%20Class.md) объект, представляющий расположение где [массива](../../../parallel/amp/reference/array-class.md) выделен объект. Это свойство может осуществляться только на ЦП.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  `accelerator_view` Объект, представляющий расположение где [массива](../../../parallel/amp/reference/array-class.md) выделен объект.  
  
##  <a name="a-namearraygetassociatedacceleratorviewmethoda-arraygetassociatedacceleratorview-method"></a><a name="array__get_associated_accelerator_view_method"></a>  Метод Array::get_associated_accelerator_view  
 Возвращает второй [accelerator_view](../Topic/accelerator_view%20Class.md) объект, который передается в качестве параметра при вызове промежуточной конструктор для создания экземпляра [массива](../../../parallel/amp/reference/array-class.md) объекта.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Второй [accelerator_view](../Topic/accelerator_view%20Class.md) объект, передаваемый конструктору промежуточной.  
  
##  <a name="a-namearraygetcpuaccesstypemethoda-arraygetcpuaccesstype-method"></a><a name="array__get_cpu_access_type_method"></a>  Метод Array::get_cpu_access_type  
 Возвращает access_type ЦП, допустимых для данного массива.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-namearraygetextentmethoda-arraygetextent-method"></a><a name="array__get_extent_method"></a>  Метод Array::get_extent  
 Возвращает [область](../Topic/extent%20Class%20\(C++%20AMP\).md) объект [массива](../../../parallel/amp/reference/array-class.md).  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  `extent` Объект [массива](../../../parallel/amp/reference/array-class.md).  
  
##  <a name="a-namearrayoperatorstdvectorltvaluetypegtoperatora-arrayoperator-stdvectorltvaluetypegt-operator"></a><a name="array__operator_std__vector_lt__value_type_gt__operator"></a>  Array::operator std::vector&lt;value_type&gt; оператор  
 Использует `copy(*this, vector)` неявное преобразование массива в объект std::vector.  
  
''' оператор std::vector \< value_type > () const restrict(cpu);
```  
  
### Parameters  
 `value_type`  
 The data type of the elements of the vector.  
  
### Return Value  
 An object of type `vector<T>` that contains a copy of the data that is contained in the array.  
  
##  <a name="array__operator___operator"></a>  array::operator() Operator  
 Returns the element value that is specified by the parameters.  
  
```  
value_type & operator() (const индекс \< _Rank > & _Index) restrict(amp,cpu);

 
const value_type & operator() (const индекс \< _Rank > & _Index) const restrict(amp,cpu);

 
value_type & restrict(amp,cpu) operator() (int _I0, int _I1);

 
const value_type & restrict(amp,cpu) const operator() (int _I0, int _I1);

 
value_type & restrict(amp,cpu) operator() (int _I0, int _I1, int _I2);

 
const value_type & restrict(amp,cpu) const operator() (int _I0, int _I1, int _I2);

 
TypeName details::_Projection_result_type \< value_type, _Rank >:: operator() (int _условия) restrict(amp,cpu) _Result_type;

 
TypeName details::_Projection_result_type \< value_type, _Rank >:: operator() (int _условия) restrict(amp,cpu) _Const_result_type const;
```  
  
### Parameters  
 `_Index`  
 The location of the element.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_I`  
 The location of the element.  
  
### Return Value  
 The element value specified by the parameters.  
  
##  <a name="array__operator_at_operator"></a>  array::operator[] Operator  
 Returns the element that is at the specified index.  
  
```  
value_type & -оператор [] (const индекс \< _Rank > & _Index) restrict(amp,cpu);

 
value_type & -оператор [] const (const индекс \< _Rank > & _Index) const restrict(amp,cpu);

 
TypeName details::_Projection_result_type \< value_type, _Rank >:: оператор _Result_type[](int _I) restrict(amp,cpu);

 
TypeName details::_Projection_result_type \< value_type, _Rank >:: оператор _Const_result_type[](int _I) const restrict(amp,cpu);
```  
  
### Parameters  
 `_Index`  
 The index.  
  
 `_I`  
 The index.  
  
### Return Value  
 The element that is at the specified index.  
  
##  <a name="array__operator_eq_operator"></a>  array::operator= Operator  
 Copies the contents of the specified [array](../../../parallel/amp/reference/array-class.md) object.  
  
```  
Массив, оператор & = (const массива & _Other) restrict(cpu);

 
Массив, оператор & = (массив & & _Other) restrict(cpu);

 
Массив, оператор & = (const array_view \< const value_type, _Rank > & _Src) restrict(cpu);
```  
  
### Parameters  
 `_Other`  
 The `array` object to copy from.  
  
 `_Src`  
 The `array` object to copy from.  
  
### Return Value  
 A reference to this `array` object.  
  
##  <a name="array__rank_constant"></a>  array::rank Constant  
 Stores the rank of the [array](../../../parallel/amp/reference/array-class.md).  
  
```  
статические const int ранг = _Rank;  
```  
  
##  <a name="array__section_method"></a>  array::section Method  
 Returns a subsection of the [array](../../../parallel/amp/reference/array-class.md) object that is at the specified origin and, optionally, that has the specified extent.  
  
```  
array_view \< value_type, _Rank > статьи (const Concurrency::index \< _Rank > & _Section_origin,  
    const Concurrency::extent \< _Rank > & _Section_extent) restrict(amp,cpu);

 
array_view \< const value_type, _Rank > статьи (const Concurrency::index \< _Rank > & _Section_origin,  
    const Concurrency::extent \< _Rank > & _Section_extent) const restrict(amp,cpu);

 
array_view \< value_type, _Rank > статьи (const Concurrency::extent \< _Rank > & _Ext) restrict(amp,cpu);

 
array_view \< const value_type, _Rank > статьи (const Concurrency::extent \< _Rank > & _Ext) const restrict(amp,cpu);

 
array_view \< value_type, _Rank > статьи (const индекс \< _Rank > & _Idx) restrict(amp,cpu);

 
array_view \< const value_type, _Rank > статьи (const индекс \< _Rank > & _Idx) const restrict(amp,cpu);

 
array_view \< value_type 1 > раздела (int _I0,  
    restrict(amp,cpu) int _E0);

 
array_view \< const value_type, 1 > раздела (int _I0,  
    const restrict(amp,cpu) int _E0);

 
array_view \< value_type 2 > раздела (int _I0,  
    int _I1  
    int _E0  
    restrict(amp,cpu) int _E1);

 
array_view \< const value_type, 2 > раздела (int _I0,  
    int _I1  
    int _E0  
    const restrict(amp,cpu) int _E1);

 
array_view \< value_type 3 > раздела (int _I0,  
    int _I1  
    int _I2  
    int _E0  
    int _E1  
    restrict(amp,cpu) int _E2);

 
array_view \< const value_type, 3 > раздела (int _I0,  
    int _I1  
    int _I2  
    int _E0  
    int _E1  
    const restrict(amp,cpu) int _E2);
```  
  
### Parameters  
 `_E0`  
 The most significant component of the extent of this section.  
  
 `_E1`  
 The next-to-most-significant component of the extent of this section.  
  
 `_E2`  
 The least significant component of the extent of this section.  
  
 `_Ext`  
 The [extent](../Topic/extent%20Class%20\(C++%20AMP\).md) object that specifies the extent of the section. The origin is 0.  
  
 `_Idx`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin. The subsection is the rest of the extent.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_Rank`  
 The rank of the section.  
  
 `_Section_extent`  
 The [extent](../Topic/extent%20Class%20\(C++%20AMP\).md) object that specifies the extent of the section.  
  
 `_Section_origin`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin.  
  
 `value_type`  
 The data type of the elements that are copied.  
  
### Return Value  
 Returns a subsection of the `array` object that is at the specified origin and, optionally, that has the specified extent. When only the `index` object is specified, the subsection contains all elements in the associated grid that have indexes that are larger than the indexes of the elements in the `index` object.  
  
##  <a name="array__view_as_method"></a>  array::view_as Method  
 Reinterprets this array as an [array_view](../../../parallel/amp/reference/array-view-class.md) of a different rank.  
  
```  
шаблон \< int _New_rank  
>  
view_as array_view \< value_type, _New_rank > (const Concurrency::extent \< _New_rank > & _View_extent) restrict(amp,cpu);

 
шаблон \< int _New_rank  
>  
array_view \< const value_type, _New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) const restrict(amp,cpu);
```  
  
### Parameters  
 `_New_rank`  
 The rank of the `extent` object passed as a parameter.  
  
 `_View_extent`  
 The extent that is used to construct the new [array_view](../../../parallel/amp/reference/array-view-class.md) object.  
  
 `value_type`  
 The data type of the elements in both the original [array](../../../parallel/amp/reference/array-class.md) object and the returned `array_view` object.  
  
### Return Value  
 The [array_view](../../../parallel/amp/reference/array-view-class.md) object that is constructed.  
  
## See Also  
 [Concurrency Namespace (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
