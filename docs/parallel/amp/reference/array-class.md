---
title: Класс array
ms.date: 11/04/2016
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
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
ms.openlocfilehash: 16d18d23c370a8a603ab6150fcee18455ae47c48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405512"
---
# <a name="array-class"></a>Класс array

Представляет контейнер данных, используемый для перемещения данных к ускорителю.

## <a name="syntax"></a>Синтаксис

```
template <typename value_type, int _Rank>
friend class array;
```

#### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип элемента данных.

*_Rank*<br/>
Ранг массива.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Массив, конструктор](#ctor)|Инициализирует новый экземпляр класса `array`.|
|[~ array деструктор](#dtor)|Уничтожает `array` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[copy_to](#copy_to)|Копирует содержимое массива в другой массив.|
|[data](#data)|Возвращает указатель на необработанные данные массива.|
|[get_accelerator_view](#get_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) , представляющий расположение, где размещен массив. Это свойство может осуществляться только на ЦП.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Возвращает второй [accelerator_view](accelerator-view-class.md) объект, который передается в качестве параметра при вызове промежуточного конструктора для создания экземпляра `array` объекта.|
|[get_cpu_access_type](#get_cpu_access_type)|Возвращает [access_type](concurrency-namespace-enums-amp.md#access_type) массива. Этот метод может осуществляться только на ЦП.|
|[get_extent](#get_extent)|Возвращает [экстент](extent-class.md) объект массива.|
|[reinterpret_as](#reinterpret_as)|Возвращает одномерный массив, содержащий все элементы в `array` объекта.|
|[section](#section)|Возвращает подраздел `array` , находящийся по заданному начальному и, при необходимости, имеющий определенный размер.|
|[view_as](#view_as)|Возвращает [array_view](array-view-class.md) объект, созданный из `array` объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[оператор std::vector&lt;value_type&gt;](#operator_vec)|Использует `copy(*this, vector)` выполнить неявное преобразование массива в объект std::[вектор](../../../standard-library/vector-class.md) объекта.|
|[operator()](#operator_call)|Возвращает значение элемента, который указан в параметрах.|
|[operator\[\]](#operator_at)|Возвращает элемент, находящийся по указанному индексу.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `array` в данный объект.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Ранг константа](#rank)|Хранит ранг массива.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[accelerator_view](#accelerator_view)|Получает [accelerator_view](accelerator-view-class.md) , представляющий расположение, где размещен массив. Это свойство может осуществляться только на ЦП.|
|[associated_accelerator_view](#associated_accelerator_view)|Возвращает второй [accelerator_view](accelerator-view-class.md) объект, который передается в качестве параметра при вызове промежуточного конструктора для создания экземпляра `array` объекта.|
|[cpu_access_type](#cpu_access_type)|Получает [access_type](concurrency-namespace-enums-amp.md#access_type) , представляющий способ доступа ЦП к хранилищу массива.|
|[extent](#extent)|Получает экстент, который определяет форму массива.|

## <a name="remarks"></a>Примечания

Тип `array<T,N>` представляет плотный и обычный (равномерный) *N*-мерный массив, который находится в определенном месте, например в ускорителе или ЦП. Тип данных элементов в массиве является `T`, который должен иметь тип, который совместим с целевым ускорителем. Несмотря на то что ранг, `N`, (из массива определяется статически и является частью типа, область памяти массива определяется средой выполнения и выражается с помощью класса `extent<N>`.

Массив может иметь любое количество измерений, несмотря на то, что некоторые функциональные возможности специализированы для `array` объектов с размерности 1, 2 и 3. Если опустить аргумент измерения, значение по умолчанию равно 1.

Данные массива располагаются последовательно в памяти. Элементы, которые отличаются на единицу в наименее значительного измерения являются смежными в памяти.

Массивы логически считаются типами значений, поскольку при копировании массива в другой массив глубокое копирование выполняется. Два массива никогда не указывают на тех же данных.

`array<T,N>` Тип используется в различных сценариях:

- Как контейнер данных, который может использоваться в вычислениях на ускорителе.

- Как контейнер данных для хранения памяти на узловом ЦП (который может использоваться для копирования и из других массивов).

- В качестве промежуточного объекта действовать как быстрый посредник в копии узла на устройство.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`array`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен:** параллелизм

##  <a name="dtor"></a> ~ array

Уничтожает `array` объекта.

```
~array() restrict(cpu);
```

##  <a name="accelerator_view"></a> accelerator_view

Получает [accelerator_view](accelerator-view-class.md) , представляющий расположение, где размещен массив. Это свойство может осуществляться только на ЦП.

```
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;
```

##  <a name="ctor"></a> Массив

Инициализирует новый экземпляр класса [класс array](array-class.md). Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы выполняются только на ЦП. Они не могут выполняться на целевом объекте Direct3D.

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

*_Associated_Av*<br/>
Объект accelerator_view, который указывает расположение предпочтительным целевым объектом для массива.

*_Av*<br/>
[Accelerator_view](accelerator-view-class.md) , указывающий расположение массива.

*_Cpu_access_type*<br/>
Требуемый [access_type](concurrency-namespace-enums-amp.md#access_type) для массива в ЦП. Этот параметр имеет значение по умолчанию `access_type_auto` оставляя ЦП `access_type` определяется средой выполнения. Фактическое ЦП `access_type` для массива можно запросить с помощью `get_cpu_access_type` метод.

*_Extent*<br/>
Границы каждого измерения массива.

*_E0*<br/>
Наиболее значимый компонент границы этого раздела.

*_E1*<br/>
Далее к наиболее значимый компонент границы этого раздела.

*_E2*<br/>
Наименее значимый компонент границы этого раздела.

*_InputIterator*<br/>
Тип итератора ввода.

*_Src*<br/>
Объект, который требуется скопировать.

*_Src_first*<br/>
Итератор с начала в исходном контейнере.

*_Src_last*<br/>
Итератор конца в исходном контейнере.

*_Другое*<br/>
Другой источник данных.

*_Rank*<br/>
Ранг раздела.

*value_type*<br/>
Тип данных элементов, которые будут скопированы.

##  <a name="associated_accelerator_view"></a> associated_accelerator_view

Возвращает второй [accelerator_view](accelerator-view-class.md) объект, который передается в качестве параметра при вызове промежуточного конструктора для создания экземпляра `array` объекта.

```
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

##  <a name="copy_to"></a> copy_to

Копирует содержимое объекта `array` в другой `array`.

```
void copy_to(
    array<value_type, _Rank>& _Dest) const ;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
[Array_view](array-view-class.md) объект для копирования.

##  <a name="cpu_access_type"></a> cpu_access_type

Получает access_type ЦП, разрешенные для этого массива.

```
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;
```

##  <a name="data"></a> Данные

Возвращает указатель на необработанные данные `array`.

```
value_type* data() restrict(amp, cpu);

const value_type* data() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на необработанные данные массива.

##  <a name="extent"></a> экстент

Получает [экстент](extent-class.md) объект, который определяет форму `array`.

```
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

##  <a name="get_accelerator_view"></a> get_accelerator_view

Возвращает [accelerator_view](accelerator-view-class.md) объект, представляющий расположение где `array` выделении объекта. Это свойство может осуществляться только на ЦП.

```
Concurrency::accelerator_view get_accelerator_view() const;
```

### <a name="return-value"></a>Возвращаемое значение

`accelerator_view` Объект, представляющий расположение где `array` выделении объекта.

##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view

Возвращает второй [accelerator_view](accelerator-view-class.md) объект, который передается в качестве параметра при вызове промежуточного конструктора для создания экземпляра `array` объекта.

```
Concurrency::accelerator_view get_associated_accelerator_view() const ;
```

### <a name="return-value"></a>Возвращаемое значение

Второй [accelerator_view](accelerator-view-class.md) объект передан в конструктор промежуточной.

##  <a name="get_cpu_access_type"></a> get_cpu_access_type

Возвращает access_type ЦП, разрешенные для этого массива.

```
access_type get_cpu_access_type() const restrict(cpu);
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="get_extent"></a> get_extent

Возвращает [экстент](extent-class.md) объект `array`.

```
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Возвращаемое значение

`extent` Объект `array`.

##  <a name="operator_vec"></a> оператор std::vector&lt;value_type&gt;

Использует `copy(*this, vector)` выполнить неявное преобразование массива в объект std::vector.

```
operator std::vector<value_type>() const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип данных элементов вектора.

### <a name="return-value"></a>Возвращаемое значение

Объект типа `vector<T>` объект, содержащий копию данных, содержащихся в массиве.

##  <a name="operator_call"></a> operator()

Возвращает значение элемента, который указан в параметрах.

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

*_Index*<br/>
Расположение элемента.

*_I0*<br/>
Наиболее значимый компонент начальной позиции этого раздела.

*_I1*<br/>
Далее к наиболее значимый компонент начальной позиции этого раздела.

*_I2*<br/>
Наименее значимый компонент начальной позиции этого раздела.

*_I*<br/>
Расположение элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, указанный параметрами.

##  <a name="operator_at"></a> оператор]

Возвращает элемент, находящийся по указанному индексу.

```
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);

const value_type& operator[]
    (const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

*_I*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Элемент, находящийся по указанному индексу.

##  <a name="operator_eq"></a> оператор =

Копирует содержимое указанного объекта `array` объекта.

```
array& operator= (const array& _Other) restrict(cpu);

array& operator= (array&& _Other) restrict(cpu);

array& operator= (
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`array` Для копирования.

*_Src*<br/>
`array` Для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `array` объекта.

##  <a name="rank"></a> Ранг

Хранит ранг объекта `array`.

```
static const int rank = _Rank;
```

## <a name="reinterpret_as"></a> reinterpret_as

Повторная интерпретация массива через одномерный array_view, который при необходимости может быть типом значения, отличным от исходного массива.

### <a name="syntax"></a>Синтаксис

```
template <typename _Value_type2>
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);

template <typename _Value_type2>
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Value_type2*<br/>
Тип данных, возвращаемых данных.

### <a name="return-value"></a>Возвращаемое значение

Array_view или константный объект array_view, который основан на массиве, с типом элемента, переработанным из T для ElementType "и" Ранг, в отличие от N до 1.

### <a name="remarks"></a>Примечания

Иногда удобно просмотреть многомерный массив, если это Линейный, одномерный массив, возможно, с типом значения, отличным от исходного массива. Этот метод можно использовать для достижения этой цели.
**Внимание** повторная интерпретация объекта массива с помощью другого типа значения является потенциально опасной операцией. Мы рекомендуем использовать эту функцию осторожно.

Ниже приведен пример кода.

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

##  <a name="section"></a> Раздел

Возвращает подраздел `array` , находящийся по заданному начальному и, при необходимости, имеющий определенный размер.

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

*_E0*<br/>
Наиболее значимый компонент границы этого раздела.

*_E1*<br/>
Далее к наиболее значимый компонент границы этого раздела.

*_E2*<br/>
Наименее значимый компонент границы этого раздела.

*_Ext*<br/>
[Экстент](extent-class.md) , указывающий границы раздела. Источником является 0.

*_Idx*<br/>
[Индекс](index-class.md) , указывающий расположение начальной позиции. Подраздел — оставшаяся часть области.

*_I0*<br/>
Наиболее значимый компонент начальной позиции этого раздела.

*_I1*<br/>
Далее к наиболее значимый компонент начальной позиции этого раздела.

*_I2*<br/>
Наименее значимый компонент начальной позиции этого раздела.

*_Rank*<br/>
Ранг раздела.

*_Section_extent*<br/>
[Экстент](extent-class.md) , указывающий границы раздела.

*_Section_origin*<br/>
[Индекс](index-class.md) , указывающий расположение начальной позиции.

*value_type*<br/>
Тип данных элементов, которые будут скопированы.

### <a name="return-value"></a>Возвращаемое значение

Возвращает подраздел `array` , находящийся по заданному начальному и, при необходимости, имеющий определенный размер. Только если `index` объект указан, то подраздел содержит все элементы в связанной таблице, которые имеют индексы, превышающие индексы элементов в `index` объекта.

##  <a name="view_as"></a> view_as

Повторная интерпретация этого массива в качестве [array_view](array-view-class.md) другого ранжирования.

```
template <int _New_rank>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

template <int _New_rank>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_New_rank*<br/>
Ранг `extent` объект, переданный в качестве параметра.

*_View_extent*<br/>
Область памяти, которая используется для создания нового [array_view](array-view-class.md) объекта.

*value_type*<br/>
Тип данных элементов, как в исходном `array` объекта и в возвращенном `array_view` объекта.

### <a name="return-value"></a>Возвращаемое значение

[Array_view](array-view-class.md) создаваемый объект.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
