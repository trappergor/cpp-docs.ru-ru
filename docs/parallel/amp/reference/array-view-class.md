---
title: "Класс array_view | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::array_view"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array_view - класс"
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс array_view
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Представляет представление N-мерный данные, хранящиеся в другой контейнер.  
  
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
 `value_type`  
 Тип данных элементов в `array_view` объекта.  
  
 `_Rank`  
 Ранг `array_view` объекта.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор array_view::array_view](#array_view__array_view_constructor)|Инициализирует новый экземпляр класса `array_view`. Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы ограничены для запуска только в ЦП и не может быть выполнена на целевом Direct3D.|  
|[array_view:: ~ array_view деструктор](#array_view___dtorarray_view_destructor)|Уничтожает `array_view` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод array_view::copy_to](#array_view__copy_to_method)|Копирует содержимое `array_view` объект в указанное назначение путем вызова `copy(*this, dest)`.|  
|[Метод array_view::Data](#array_view__data_method)|Возвращает указатель на необработанные данные `array_view`.|  
|[Метод array_view::discard_data](#array_view__discard_data_method)|Удаляет текущий базовые данные этого представления.|  
|[Метод array_view::get_extent](#array_view__get_extent_method)|Возвращает объект экстента array_view объекта.|  
|[Метод array_view::get_ref](#array_view__get_ref_method)|Возвращает ссылку на индексированного элемента.|  
|[Метод array_view::get_source_accelerator_view](#array_view__get_source_accelerator_view_method)|Возвращает [accelerator_view](../Topic/accelerator_view%20Class.md) где источник данных `array_view` находится.|  
|[Метод array_view::Refresh](#array_view__refresh_method)|Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейса. Вызов этого метода отображает все кэшированные данные устаревшим.|  
|[Метод array_view::reinterpret_as](#array_view__reinterpret_as_method)|Возвращает одномерный массив, содержащий все элементы в `array_view` объекта.|  
|[Метод array_view::Section](#array_view__section_method)|Возвращает подраздел `array_view` объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область.|  
|[Метод array_view::Synchronize](#array_view__synchronize_method)|Синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.|  
|[Метод array_view::synchronize_async](#array_view__synchronize_async_method)|Асинхронно синхронизирует любые изменения, внесенные в [array_view](../../../parallel/amp/reference/array-view-class.md) объекта обратно в исходные данные.|  
|[Метод array_view::synchronize_to](#array_view__synchronize_to_method)|Синхронизирует любые изменения, внесенные в `array_view` объекта на указанное [accelerator_view](../Topic/accelerator_view%20Class.md).|  
|[Метод array_view::synchronize_to_async](#array_view__synchronize_to_async_method)|Асинхронно синхронизирует любые изменения, внесенные в `array_view` объекта на указанное [accelerator_view](../Topic/accelerator_view%20Class.md).|  
|[Метод array_view::view_as](#array_view__view_as_method)|Создает `array_view` объекта с помощью другого ранга `array_view` данных объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор array_view:: operator()](#array_view__operator___operator)|Возвращает значение элемента, который определяется один или несколько параметров.|  
|[Оператор array_view::operator]](#array_view__operator_at_operator)|Возвращает элемент, указанный в параметрах.|  
|[array_view::operator =-оператор](#array_view__operator_eq_operator)|Копирует содержимое указанного `array_view` объекта в другой.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа array_view::Rank](#array_view__rank_constant)|Сохраняет ранг объекта `array_view` объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[элемент данных array_view::Extent](#array_view__extent_data_member)|Получает объект `extent`, который определяет форму объекта `array_view`.|  
|[элемент данных array_view::source_accelerator_view](#array_view__source_accelerator_view_data_member)|Возвращает [accelerator_view](../Topic/accelerator_view%20Class.md) где источник данных `array_view` находится|  
|[элемент данных array_view::value_type](#array_view__value_type_data_member)|Тип значения `array_view` и связанного массива.|  
  
## <a name="remarks"></a>Примечания  
  `array_view` Класс представляет представление данных, которое содержится в [массива](../../../parallel/amp/reference/array-class.md) объекта или подраздел `array` объекта.  
  
 Можно получить доступ к `array_view` объекта, где источник данных расположен (локально) или в различных сочетаний клавиш или домене согласованности (удаленно). Когда доступ к объекту удаленно, представления копируются и кэшируются при необходимости. За исключением эффекты автоматического кэширования `array_view` объекты имеют показатели производительности, аналогичен `array` объектов. При небольших производительности доступа к данным через представления.  
  
 Существует три варианта пульт дистанционного управления:  
  
-   Представление указателя памяти системы передается с помощью параметра [parallel_for_each](concurrency%20namespace%20functions.md#parallel_for_each) вызов ускоритель и доступ осуществляется через сочетания клавиш.  
  
-   Представление в массив, расположенных на ускоритель передается с помощью параметра `parallel_for_each` вызов другого сочетаний клавиш и осуществляется.  
  
-   Представление в массив, расположенных на ускоритель осуществляется на ЦП.  
  
 В любом из этих сценариев, упоминаемого представления копируются средой выполнения в удаленном расположении и, если изменен на вызовы `array_view` объекта, копируются обратно в локальное расположение. Среда выполнения может оптимизировать процесс копирования изменений обратно, может копировать только измененные элементы или может также скопируйте фрагменты без изменений. Перекрывающиеся `array_view` объектов в одном источнике данных не гарантируется для поддержания целостности данных в удаленном расположении.  
  
 Необходимо синхронизировать многопоточного доступа к тому же источнику данных.  
  
 Среда выполнения предоставляет следующие гарантии относительно кэширование данных в `array_view` объектов:  
  
-   Все хорошо синхронизированный доступ к `array` объекта и `array_view` объекта на нем в порядке программы подчиняются последовательное происходит-перед связь.  
  
-   Хорошо синхронизированных доступ к перекрывающимся `array_view` объекты на же сочетания клавиш на одном `array` объекта используются псевдонимы через `array` объекта. Они вызывать всего происходит-перед отношение, которое подчиняется порядка в программе. Не выполняется кэширование. Если `array_view` объекты выполняются на разных ускорители, порядок доступа не определен, создание состояние гонки.  
  
 При создании `array_view` объекта с помощью указателя в системной памяти, необходимо изменить представление `array_view` только с помощью объекта `array_view` указателя. Кроме того, необходимо вызвать метод `refresh()` на одном из `array_view` объектов, присоединенных к указателю системы базовой внутренней памяти при изменении напрямую, а не через `array_view` объекта.  
  
 В обоих случаях сообщает `array_view` объекта изменении базовых внутренней памяти и что все копии, которые находятся в ускоритель устарели. Если следовать рекомендациям представления на основе указателя идентичны для представления данных параллельными массивами.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="a-namearrayviewdtorarrayviewdestructora-arrayviewarrayview-destructor"></a><a name="array_view___dtorarray_view_destructor"></a>  array_view:: ~ array_view деструктор  
 Уничтожает [array_view](../../../parallel/amp/reference/array-view-class.md) объекта.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="a-namearrayviewarrayviewconstructora-arrayviewarrayview-constructor"></a><a name="array_view__array_view_constructor"></a>  Конструктор array_view::array_view  
 Инициализирует новый экземпляр [array_view](../../../parallel/amp/reference/array-view-class.md) класса.  
  
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
 `_Arr_type`  
 Тип элементов массива C-стиль, из которой данные передаются.  
  
 `_Container`  
 Аргумент шаблона, который необходимо указать линейной контейнера, который поддерживает `data()` и `size()` члены.  
  
 `_E0`  
 Наиболее значимые компонент экстента в этом разделе.  
  
 `_E1`  
 Далее к значащий компонент экстента в этом разделе.  
  
 `_E2`  
 Компонент младших экстента в этом разделе.  
  
 `_Extent`  
 Экстент в каждой размерности `array_view`.  
  
 `_Other`  
 Объект типа `array_view<T,N>` для инициализации нового `array_view`.  
  
 `_Size`  
 Размер массива стиле C, из которой данные передаются.  
  
 `_Src`  
 Указатель на исходные данные, которые будут скопированы в новый массив.  
  
##  <a name="a-namearrayviewcopytomethoda-arrayviewcopyto-method"></a><a name="array_view__copy_to_method"></a>  Метод array_view::copy_to  
 Копирует содержимое [array_view](../../../parallel/amp/reference/array-view-class.md) в указанный конечный объект, вызвав `copy(*this, dest)`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Объект для копирования.  
  
##  <a name="a-namearrayviewdatamethoda-arrayviewdata-method"></a><a name="array_view__data_method"></a>  Метод array_view::Data  
 Возвращает указатель на необработанные данные [array_view](../../../parallel/amp/reference/array-view-class.md).  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные `array_view`.  
  
##  <a name="a-namearrayviewdiscarddatamethoda-arrayviewdiscarddata-method"></a><a name="array_view__discard_data_method"></a>  Метод array_view::discard_data  
 Удаляет текущий базовые данные этого представления. Это позволяет избежать копирования текущее содержимое представления в целевой среде выполнения указание по оптимизации `accelerator_view` при доступе к, и его использование рекомендуется, если нет необходимости существующего содержимого. Этот метод является холостой при использовании в контексте restrict(amp)  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewextentdatamembera-arrayviewextent-data-member"></a><a name="array_view__extent_data_member"></a>  элемент данных array_view::Extent  
 Получает объект `extent`, который определяет форму объекта `array_view`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearrayviewgetextentmethoda-arrayviewgetextent-method"></a><a name="array_view__get_extent_method"></a>  Метод array_view::get_extent  
 Возвращает [область](../Topic/extent%20Class%20\(C++%20AMP\).md) объект [array_view](../../../parallel/amp/reference/array-view-class.md) объекта.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  `extent` Объект `array_view` объект  
  
##  <a name="a-namearrayviewgetrefmethoda-arrayviewgetref-method"></a><a name="array_view__get_ref_method"></a>  Метод array_view::get_ref  
 Получите ссылку на элемент с _Index индексом. В отличие от других индексирования операторов для доступа к array_view на ЦП этот метод не выполняет синхронизацию неявно содержимое этого array_view для ЦП. После доступа к array_view в удаленном расположении или выполнение операции копирования, включающие этот array_view пользователей отвечают явно синхронизации array_view для ЦП перед вызовом этого метода. Невыполнение этого требования приведет к неопределенному поведению.  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент с _Index индексом  
  
##  <a name="a-namearrayviewgetsourceacceleratorviewmethoda-arrayviewgetsourceacceleratorview-method"></a><a name="array_view__get_source_accelerator_view_method"></a>  Метод array_view::get_source_accelerator_view  
 Возвращает accelerator_view, где находится источник данных array_view. Если array_view имеет источник данных, этот интерфейс API вызывает runtime_exception  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-namearrayviewoperatoroperatora-arrayviewoperator-operator"></a><a name="array_view__operator___operator"></a>  Оператор array_view:: operator()  
 Возвращает значение элемента, который определяется один или несколько параметров.  
  
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
 `_Index`  
 Расположение элемента.  
  
 `_I0`  
 Индекс в первом измерении.  
  
 `_I1`  
 Индекс во втором измерении.  
  
 `_I2`  
 Индекс в третьем измерении.  
  
 `_I`  
 Расположение элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, который определяется один или несколько параметров.  
  
##  <a name="a-namearrayviewoperatoratoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_at_operator"></a>  Оператор array_view::operator]  
 Возвращает элемент, указанный в параметрах.  
  
```  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

 
value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс.  
  
 `_I`  
 Индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента по индексу или `array_view` проецируется на наиболее значимых измерения.  
  
##  <a name="a-namearrayviewoperatoreqoperatora-arrayviewoperator-operator"></a><a name="array_view__operator_eq_operator"></a>  array_view::operator =-оператор  
 Копирует содержимое указанного [array_view](../../../parallel/amp/reference/array-view-class.md) этого объекта.  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
  `array_view` Для копирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `array_view` объекта.  
  
##  <a name="a-namearrayviewrankconstanta-arrayviewrank-constant"></a><a name="array_view__rank_constant"></a>  Константа array_view::Rank  
 Сохраняет ранг объекта [array_view](../../../parallel/amp/reference/array-view-class.md) объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namearrayviewrefreshmethoda-arrayviewrefresh-method"></a><a name="array_view__refresh_method"></a>  Метод array_view::Refresh  
 Уведомляет [array_view](../../../parallel/amp/reference/array-view-class.md) объекта, привязанного памяти был изменен вне `array_view` интерфейса. Вызов этого метода отображает все кэшированные данные устаревшим.  
  
```  
void refresh() const restrict(cpu);
```  
  
##  <a name="a-namearrayviewsectionmethoda-arrayviewsection-method"></a><a name="array_view__section_method"></a>  Метод array_view::Section  
 Возвращает подраздел [array_view](../../../parallel/amp/reference/array-view-class.md) объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область.  
  
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
 `_E0`  
 Наиболее значимые компонент экстента в этом разделе.  
  
 `_E1`  
 Далее к значащий компонент экстента в этом разделе.  
  
 `_E2`  
 Компонент младших экстента в этом разделе.  
  
 `_Ext`  
  [Экстент](../Topic/extent%20Class%20\(C++%20AMP\).md) объекта, который задает область раздела. Источником является 0.  
  
 `_Idx`  
  [Индекс](../../../parallel/amp/reference/index-class.md) объект, который указывает расположение начала координат. Подраздел является rest экстента.  
  
 `_I0`  
 Наиболее значимые компонент источника в этом разделе.  
  
 `_I1`  
 Далее к значащий компонент источника в этом разделе.  
  
 `_I2`  
 Младший компонент источника в этом разделе.  
  
 `_Rank`  
 Ранг раздела.  
  
 `_Section_extent`  
  [Экстент](../Topic/extent%20Class%20\(C++%20AMP\).md) объекта, который задает область раздела.  
  
 `_Section_origin`  
  [Индекс](../../../parallel/amp/reference/index-class.md) объект, который указывает расположение начала координат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подраздел `array_view` объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область. Только если `index` объект указан, подраздел содержит все элементы в экстенте связанные, имеют индексы, превышающие индексы элементов в `index` объекта.  
  
##  <a name="a-namearrayviewsourceacceleratorviewdatamembera-arrayviewsourceacceleratorview-data-member"></a><a name="array_view__source_accelerator_view_data_member"></a>  элемент данных array_view::source_accelerator_view  
 Возвращает источник accelerator_view, связанный с этой array_view.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="a-namearrayviewsynchronizemethoda-arrayviewsynchronize-method"></a><a name="array_view__synchronize_method"></a>  Метод array_view::Synchronize  
 Синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Access_type`  
 Предполагаемого [access_type](concurrency%20namespace%20enums.md#access_type) на целевом [accelerator_view](../Topic/accelerator_view%20Class.md). Этот параметр имеет значение по умолчанию `access_type_read`.  
  
##  <a name="a-namearrayviewsynchronizeasyncmethoda-arrayviewsynchronizeasync-method"></a><a name="array_view__synchronize_async_method"></a>  Метод array_view::synchronize_async  
 Асинхронно синхронизирует любые изменения, внесенные в [array_view](../../../parallel/amp/reference/array-view-class.md) объекта обратно в исходные данные.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Access_type`  
 Предполагаемого [access_type](concurrency%20namespace%20enums.md#access_type) на целевом [accelerator_view](../Topic/accelerator_view%20Class.md). Этот параметр имеет значение по умолчанию `access_type_read`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее, на которой будет ожидать завершения операции.  
  
##  <a name="a-namearrayviewsynchronizetomethoda-arrayviewsynchronizeto-method"></a><a name="array_view__synchronize_to_method"></a>  Метод array_view::synchronize_to  
 Синхронизирует любые изменения, внесенные в этот array_view для указанного accelerator_view.  
  
```  
void synchronize_to(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Accl_view`  
 Accelerator_view целевой для синхронизации.  
  
 `_Access_type`  
 Требуемый access_type на целевой accelerator_view. Этот параметр имеет значение по умолчанию access_type_read.  
  
##  <a name="a-namearrayviewsynchronizetoasyncmethoda-arrayviewsynchronizetoasync-method"></a><a name="array_view__synchronize_to_async_method"></a>  Метод array_view::synchronize_to_async  
 Асинхронно синхронизирует любые изменения, внесенные в этот array_view для указанного accelerator_view.  
  
```  
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Accl_view`  
 Accelerator_view целевой для синхронизации.  
  
 `_Access_type`  
 Требуемый access_type на целевой accelerator_view. Этот параметр имеет значение по умолчанию access_type_read.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее, на которой будет ожидать завершения операции.  
  
##  <a name="a-namearrayviewvaluetypedatamembera-arrayviewvaluetype-data-member"></a><a name="array_view__value_type_data_member"></a>  элемент данных array_view::value_type  
 Тип значения array_view и связанного массива.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="a-namearrayviewviewasmethoda-arrayviewviewas-method"></a><a name="array_view__view_as_method"></a>  Метод array_view::view_as  
 Повторно интерпретирует это `array_view` как `array_view` другого ранга.  
  
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
 `_New_rank`  
 Ранг нового `array_view` объекта.  
  
 `_View_extent`  
 Изменение формы `extent`.  
  
 `value_type`  
 Тип данных элементов в исходные [массива](../../../parallel/amp/reference/array-class.md) объекта и возвращаемый `array_view` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
  [Array_view](../../../parallel/amp/reference/array-view-class.md) объект.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
