---
title: Класс array_view
ms.date: 11/04/2016
f1_keywords:
- array_view
- AMP/array_view
- AMP/Concurrency::array_view::array_view
- AMP/Concurrency::array_view::copy_to
- AMP/Concurrency::array_view::data
- AMP/Concurrency::array_view::discard_data
- AMP/Concurrency::array_view::get_extent
- AMP/Concurrency::array_view::get_ref
- AMP/Concurrency::array_view::get_source_accelerator_view
- AMP/Concurrency::array_view::refresh
- AMP/Concurrency::array_view::reinterpret_as
- AMP/Concurrency::array_view::section
- AMP/Concurrency::array_view::synchronize
- AMP/Concurrency::array_view::synchronize_async
- AMP/Concurrency::array_view::synchronize_to
- AMP/Concurrency::array_view::synchronize_to_async
- AMP/Concurrency::array_view::view_as
- AMP/Concurrency::array_view::rank
- AMP/Concurrency::array_view::extent
- AMP/Concurrency::array_view::source_accelerator_view
- AMP/Concurrency::array_view::value_type
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
ms.openlocfilehash: e73639ffd11e08edb2fdb03471f2c6c88730f02d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405564"
---
# <a name="arrayview-class"></a>Класс array_view

Представляет N-размерным представлением данных, содержащихся в другом контейнере.

## <a name="syntax"></a>Синтаксис

```
template <
    typename value_type,
    int _Rank = 1
>
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;

template <
    typename value_type,
    int _Rank
>
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;
```

#### <a name="parameters"></a>Параметры

*value_type*<br/>
Тип данных элементов в `array_view` объекта.

*_Rank*<br/>
Ранг `array_view` объекта.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Конструктор array_view](#ctor)|Инициализирует новый экземпляр класса `array_view`. Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы могут выполняться только на ЦП и не может быть выполнена на целевом объекте Direct3D.|
|[~ array_view, деструктор](#ctor)|Уничтожает `array_view` объекта.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[copy_to](#copy_to)|Копирует содержимое объекта `array_view` объект в указанное место назначения путем вызова `copy(*this, dest)`.|
|[data](#data)|Возвращает указатель на необработанные данные `array_view`.|
|[discard_data](#discard_data)|Сбрасывает текущие данные для этого представления.|
|[get_extent](#get_extent)|Возвращает объект границы объекта array_view.|
|[get_ref](#get_ref)|Возвращает ссылку на индексированный элемент.|
|[get_source_accelerator_view](#get_source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) где источник данных `array_view` находится.|
|[обновления](#refresh)|Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейс. Вызов этого метода отображает все кэшированные данные устаревшим.|
|[reinterpret_as](#reinterpret_as)|Возвращает одномерный массив, содержащий все элементы в `array_view` объекта.|
|[section](#section)|Возвращает подраздел `array_view` , находящийся по заданному начальному и, при необходимости, имеющий определенный размер.|
|[synchronize](#synchronize)|Синхронизирует все изменения, внесенные `array_view` объекта обратно в исходные данные.|
|[synchronize_async](#synchronize_async)|Асинхронно синхронизирует все изменения, внесенные `array_view` объекта обратно в исходные данные.|
|[synchronize_to](#synchronize_to)|Синхронизирует все изменения, внесенные `array_view` объекта в указанный [accelerator_view](accelerator-view-class.md).|
|[synchronize_to_async](#synchronize_to_async)|Асинхронно синхронизирует все изменения, внесенные `array_view` объекта в указанный [accelerator_view](accelerator-view-class.md).|
|[view_as](#view_as)|Создает `array_view` объекта из другого ранга, используя `array_view` данные объекта.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[operator()](#operator_call)|Возвращает значение элемента, который задается параметром или параметрами.|
|[operator\[\]](#operator_at)|Возвращает элемент, задаваемый параметрами.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `array_view` в данный объект.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Ранг константа](#rank)|Хранит ранг объекта `array_view` объекта.|

### <a name="data-members"></a>Элементы данных

|name|Описание|
|----------|-----------------|
|[extent](#extent)|Получает объект `extent`, который определяет форму объекта `array_view`.|
|[source_accelerator_view](#source_accelerator_view)|Получает [accelerator_view](accelerator-view-class.md) где источник данных `array_view` находится|
|[value_type](#value_type)|Тип значения `array_view` и ограниченного массива.|

## <a name="remarks"></a>Примечания

`array_view` Класс представляет представление данных, содержащийся в [массива](array-class.md) объекта или подраздел `array` объекта.

Вы можете получить доступ к `array_view` объекта, где источник данных находится (локально) или на другом ускорителе, или на связанном домене (удаленно). При доступе к объекту удаленно, представления копируются и кэшируются по мере необходимости. За исключением эффектов автоматического кэширования `array_view` объекты имеют профиль производительности, аналогичны `array` объектов. Нет небольшое снижение производительности при доступе к данным через представления.

Существует три сценария удаленного использования:

- Представления указателя системной памяти передается с помощью параметра [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) вызов ускорителе и непосредственным доступом на ускорителе.

- Представление для массива, расположенного на ускорителе передается с помощью параметра `parallel_for_each` вызова на другом ускорителе и непосредственным доступом на нем.

- Представление для массива, расположенного на ускорителе, осуществляется в ЦП.

В любом из этих сценариев, упомянутые представления копируются средой выполнения в удаленное расположение и при их изменении посредством вызовов к `array_view` объекта, будут скопированы обратно в локальное расположение. Среда выполнения может оптимизировать процесс копирования изменений обратно, может копировать только измененные элементы или может копировать и Неизменившиеся части также. Перекрывающиеся `array_view` объектов в одном источнике данных не гарантируется ссылочной целостности в удаленном расположении.

Необходимо синхронизировать любой многопоточный доступ к тому же источнику данных.

Среда выполнения предоставляет следующие гарантии относительно кэширования данных в `array_view` объектов:

- Любой правильно синхронизированный доступ к `array` объект и объект `array_view` объекта на него в программном порядке подчиняются последовательной передачи происходит-перед связи.

- Любой правильно синхронизированный доступ к перекрывающимся `array_view` объекты на том же ускорителе на одном `array` объект псевдоименуется с помощью `array` объекта. Они задают общее происходит-перед отношение, которое подчиняется программном порядке. Не выполняется кэширование. Если `array_view` объекты выполняются на разных ускорителях, то порядок доступа не определен, создавая состояние гонки.

При создании `array_view` объекта с помощью указателя в системной памяти, необходимо изменить представление `array_view` только через `array_view` указатель. Кроме того, необходимо вызвать `refresh()` на одном из `array_view` объекты, присоединенные к системному указателю, если нижележащая основная память изменяется напрямую, вместо использования `array_view` объекта.

Любое действие уведомляет `array_view` объекта, что нижележащая основная память изменяется, и что все копии, которые находятся на ускорителе, устарели. Если вы следуете рекомендациям, представлений на основе указателя идентичны указанным к представлениям массивов параллельной обработки данных.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`_Array_view_shape`

`_Array_view_base`

`array_view`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен:** параллелизм

##  <a name="dtor"></a> ~array_view

Уничтожает `array_view` объекта.

```
~array_view()restrict(amp,cpu);
```

##  <a name="ctor"></a> array_view

Инициализирует новый экземпляр класса `array_view`.

```
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view& _Other)restrict(amp,cpu);

explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    _Container& _Src) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    int _E0,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    _Container& _Src) restrict(cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2) __CPU_ONLY;

template <
    typename _Container
>
explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _Container& _Src);

explicit array_view(
    int _E0,
    _In_ value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    _In_ value_type* _Src)restrict(amp,cpu);

explicit array_view(
    int _E0,
    int _E1,
    int _E2,
    _In_ value_type* _Src)restrict(amp,cpu);

array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const _Container& _Src) restrict(cpu);

template <
    typename _Container
>
explicit array_view(
    const _Container& _Src,
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

array_view(
    const Concurrency::extent<_Rank>& _Extent,
    const value_type* _Src)restrict(amp,cpu);

template <
    typename _Arr_type,
    int _Size
>
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

template <
    typename _Container
>
array_view(
    int _E0,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    const _Container& _Src);

template <
    typename _Container
>
array_view(
    int _E0,
    int _E1,
    int _E2,
    const _Container& _Src);

array_view(
    int _E0,
    const value_type* _Src)restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    const value_type* _Src) restrict(amp,cpu);

array_view(
    int _E0,
    int _E1,
    int _E2,
    const value_type* _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Arr_type*<br/>
Тип элементов массива C-стиля, из которого данные передаются.

*_Container*<br/>
Аргумент шаблона, который должен определить линейный контейнер, поддерживающий `data()` и `size()` членов.

*_E0*<br/>
Наиболее значимый компонент границы этого раздела.

*_E1*<br/>
Далее к наиболее значимый компонент границы этого раздела.

*_E2*<br/>
Наименее значимый компонент границы этого раздела.

*_Extent*<br/>
Область памяти в каждом измерении этого `array_view`.

*_Другое*<br/>
Объект типа `array_view<T,N>` из которого инициализируется новый `array_view`.

*_Размер*<br/>
Размер массива C-стиля, из которого данные передаются.

*_Src*<br/>
Указатель на исходные данные, которые будут скопированы в новый массив.

##  <a name="copy_to"></a> copy_to

Копирует содержимое объекта `array_view` в указанный конечный объект, вызвав `copy(*this, dest)`.

```
void copy_to(
    array<value_type, _Rank>& _Dest) const;

void copy_to(
    array_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Параметры

*_Dest*<br/>
Объект для копирования.

##  <a name="data"></a> Данные

Возвращает указатель на необработанные данные `array_view`.

```
value_type* data() const restrict(amp,
    cpu);

const value_type* data() const restrict(amp,
    cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на необработанные данные `array_view`.

##  <a name="discard_data"></a> discard_data

Сбрасывает текущие данные для этого представления. Это указание по оптимизации в среду выполнения, используемая для избежания копирования текущего содержимого представления в целевой объект `accelerator_view` , при доступе к, и ее использование рекомендуется в том случае, если существующее содержимое не требуется. Этот метод является холостой в контексте restrict(amp)

```
void discard_data() const restrict(cpu);
```

##  <a name="extent"></a> экстент

Получает объект `extent`, который определяет форму объекта `array_view`.

```
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;
```

##  <a name="get_extent"></a> get_extent

Возвращает [экстент](extent-class.md) объект `array_view` объекта.

```
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```

### <a name="return-value"></a>Возвращаемое значение

`extent` Объект `array_view` объекта

##  <a name="get_ref"></a> get_ref

Получите ссылку на элемент, индексированный by _Index. В отличие от других операторов индексирования для доступа к array_view на ЦП этот метод не выполняет неявной синхронизации содержимого array_view с ЦП. После обращения к array_view в удаленном расположении или выполнение операции копирования с участием этого array_view пользователи должны явно синхронизировать array_view с ЦП, перед вызовом этого метода. Невыполнение этого требования приведет к неопределенному поведению.

```
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на элемент, индексированный by_index

##  <a name="get_source_accelerator_view"></a> get_source_accelerator_view

Возвращает accelerator_view, где находится источник данных array_view. Если array_view не имеет источника данных, этот API выдает runtime_exception

```
accelerator_view get_source_accelerator_view() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_call"></a> operator()

Возвращает значение элемента, который задается параметром или параметрами.

```
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1) const restrict(amp,cpu);

value_type& operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp,cpu);

typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Расположение элемента.

*_I0*<br/>
Индекс в первом измерении.

*_I1*<br/>
Индекс во втором измерении.

*_I2*<br/>
Индекс в третьем измерении.

*_I*<br/>
Расположение элемента.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента, который задается параметром или параметрами.

##  <a name="operator_at"></a> оператор]

Возвращает элемент, задаваемый параметрами.

```
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс.

*_I*<br/>
Индекс.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента по индексу или `array_view` спроецированное на наиболее значительное измерение.

##  <a name="operator_eq"></a> оператор =

Копирует содержимое указанного объекта `array_view` в данный объект.

```
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`array_view` Для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `array_view` объекта.

##  <a name="rank"></a> Ранг

Хранит ранг объекта `array_view` объекта.

```
static const int rank = _Rank;
```

##  <a name="refresh"></a> обновления

Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейс. Вызов этого метода отображает все кэшированные данные устаревшим.

```
void refresh() const restrict(cpu);
```

## <a name="reinterpret_as"></a> reinterpret_as

Повторная интерпретация array_view через одномерный array_view, который при необходимости может быть типом другим значением, отличным от исходного array_view.

### <a name="syntax"></a>Синтаксис

```
template <
    typename _Value_type2
>
array_view< _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);

template <
    typename _Value_type2
>
array_view<const _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Value_type2*<br/>
Тип данных нового `array_view` объекта.

### <a name="return-value"></a>Возвращаемое значение

`array_view` Или объект const `array_view` , основанный на этом `array_view`, с типом элементов, преобразованным из `T` для `_Value_type2`, и рангом, уменьшенном от *N* 1.

### <a name="remarks"></a>Примечания

Иногда удобно просмотреть многомерный массив как линейный, одномерный массив, который может быть типом другим значением, отличным от исходного массива. Этого можно добиться в `array_view` с помощью этого метода.

**Предупреждение** повторная интерпретация объекта array_view с помощью другого типа значения является потенциально опасной операцией. Эту функцию следует использовать с осторожностью.

Ниже приведен пример:

```cpp
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...;
array_view<float,1> v = a.reinterpret_as<float>();

assert(v.extent == 3*a.extent);
```

##  <a name="section"></a> Раздел

Возвращает подраздел `array_view` , находящийся по заданному начальному и, при необходимости, имеющий определенный размер.

```
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _E0) const restrict(amp,cpu);

array_view section(
    int _I0,
    int _I1,
    int _E0,
    int _E1) const restrict(amp,cpu);

array_view section(
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

### <a name="return-value"></a>Возвращаемое значение

Подраздел `array_view` , находящийся по заданному начальному и, при необходимости, имеющий определенный размер. Только если `index` объект указан, то подраздел содержит все элементы в соответствующих границах, имеют индексы, превышающие индексы элементов в `index` объекта.

##  <a name="source_accelerator_view"></a> source_accelerator_view

Получает source accelerator_view, с которой связан данный array_view.

```
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;
```

##  <a name="synchronize"></a> синхронизировать

Синхронизирует все изменения, внесенные `array_view` объекта обратно в исходные данные.

```
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize() const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Access_type*<br/>
Предполагаемая [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом объекте [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.

##  <a name="synchronize_async"></a> synchronize_async

Асинхронно синхронизирует все изменения, внесенные `array_view` объекта обратно в исходные данные.

```
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_async() const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Access_type*<br/>
Предполагаемая [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом объекте [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.

### <a name="return-value"></a>Возвращаемое значение

Объект фьючерса для ожидания завершения операции.

##  <a name="synchronize_to"></a> synchronize_to

Синхронизирует все изменения, внесенные в объект array_view с определенным accelerator_view.

```
void synchronize_to(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Accl_view*<br/>
К accelerator_view целевого объекта для синхронизации.

*_Access_type*<br/>
Нужный access_type в целевом accelerator_view. Этот параметр имеет значение по умолчанию access_type_read.

##  <a name="synchronize_to_async"></a> synchronize_to_async

Асинхронно синхронизирует все изменения, внесенные в объект array_view с определенным accelerator_view.

```
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,
    access_type _Access_type = access_type_read) const restrict(cpu);

concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```

### <a name="parameters"></a>Параметры

*_Accl_view*<br/>
К accelerator_view целевого объекта для синхронизации.

*_Access_type*<br/>
Нужный access_type в целевом accelerator_view. Этот параметр имеет значение по умолчанию access_type_read.

### <a name="return-value"></a>Возвращаемое значение

Объект фьючерса для ожидания завершения операции.

##  <a name="value_type"></a> value_type

Тип значения array_view и ограниченного массива.

```
typedef typenamevalue_type value_type;
```

##  <a name="view_as"></a> view_as

Повторная интерпретация `array_view` как `array_view` другого ранжирования.

```
template <
    int _New_rank
>
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

template <
    int _New_rank
>
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_New_rank*<br/>
Ранг нового `array_view` объекта.

*_View_extent*<br/>
Изменяемый объект `extent`.

*value_type*<br/>
Тип данных элементов, как в исходном [массива](array-class.md) объекта и в возвращенном `array_view` объекта.

### <a name="return-value"></a>Возвращаемое значение

`array_view` Создаваемый объект.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
