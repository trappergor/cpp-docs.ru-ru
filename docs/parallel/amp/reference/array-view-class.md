---
title: "Класс array_view | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: e921ae841aa1eade25fdf2ec272039cc41007a9e
ms.lasthandoff: 03/31/2017

---
# <a name="arrayview-class"></a>Класс array_view
Представляет представление многомерном над данными, хранящимися в другой контейнер.  
  
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
|[Конструктор array_view](#ctor)|Инициализирует новый экземпляр класса `array_view`. Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы ограничены для выполнения только в ЦП и не может быть выполнена на целевом Direct3D.|  
|[~ array_view, деструктор](#ctor)|Уничтожает `array_view` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[copy_to](#copy_to)|Копирует содержимое `array_view` указанное назначение путем вызова `copy(*this, dest)`.|  
|[data](#data)|Возвращает указатель на необработанные данные `array_view`.|  
|[discard_data](#discard_data)|Удаляет текущий базовые данные этого представления.|  
|[get_extent](#get_extent)|Возвращает объект экстента array_view объекта.|  
|[get_ref](#get_ref)|Возвращает ссылку на индексированного элемента.|  
|[get_source_accelerator_view](#get_source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) где источник данных `array_view` находится.|  
|[обновления](#refresh)|Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейса. Вызов этого метода отображает все данные из кэша устаревшим.|  
|[reinterpret_as](#reinterpret_as)|Возвращает одномерный массив, который содержит все элементы в `array_view` объекта.|  
|[section](#section)|Возвращает подраздел `array_view` объект, находящийся в указанный источник и, возможно, который имеет указанную область.|  
|[synchronize](#synchronize)|Синхронизирует все изменения, внесенные в `array_view` объекта обратно в исходные данные.|  
|[synchronize_async](#synchronize_async)|Асинхронно синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.|  
|[synchronize_to](#synchronize_to)|Синхронизирует все изменения, внесенные в `array_view` объект в указанный [accelerator_view](accelerator-view-class.md).|  
|[synchronize_to_async](#synchronize_to_async)|Асинхронно синхронизирует любые изменения, внесенные в `array_view` объект в указанный [accelerator_view](accelerator-view-class.md).|  
|[view_as](#view_as)|Создает `array_view` объекта с помощью другого ранга `array_view` данных объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Operator()](#operator_call)|Возвращает значение элемента, который задается параметром или параметрами.|  
|[оператор]](#operator_at)|Возвращает элемент, указанный параметрами.|  
|[operator=](#operator_eq)|Копирует содержимое указанного `array_view` объекта в другой.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Сохраняет ранг объекта `array_view` объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[extent](#extent)|Получает объект `extent`, который определяет форму объекта `array_view`.|  
|[source_accelerator_view](#source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) где источник данных `array_view` находится|  
|[value_type](#value_type)|Тип значения `array_view` и связанный массив.|  
  
## <a name="remarks"></a>Примечания  
 `array_view` Класс представляет представление данных, содержащихся в [массива](array-class.md) объекта или подраздел `array` объекта.  
  
 Вы можете получить доступ к `array_view` объекта, где источник данных расположен (локально) или на разных сочетаний клавиш или домен согласованность (удаленно). Если доступ к объекту удаленно, представления копируются и кэшируются при необходимости. За исключением эффекты автоматического кэширования `array_view` объекты имеют показатели производительности, аналогичные `array` объектов. Нет снижение производительности при доступе к данным через представления.  
  
 Существует три варианта удаленное использование:  
  
-   Представление, чтобы указатель памяти системы передается с помощью [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) вызов ускоритель и доступе к сочетания клавиш.  
  
-   Представление в массив, расположенный на ускорителе передается с помощью параметра `parallel_for_each` вызов другой сочетаний клавиш и осуществляется.  
  
-   Представление в массив, расположенный на ускорителе при доступе к ЦП.  
  
 В любом из этих сценариев, упоминаемого представления копируются средой выполнения в удаленном расположении и, если изменен на вызовы `array_view` объекта, будут скопированы обратно в локальное расположение. Среда выполнения может оптимизировать процесс копирования изменений обратно, может копировать только измененные элементы или может также копирование фрагментов без изменений. Перекрывающиеся `array_view` объектов на один источник данных не гарантируется для поддержания целостности данных в удаленном расположении.  
  
 Необходимо синхронизировать многопоточного доступа к тому же источнику данных.  
  
 Среда выполнения предоставляет следующие гарантии относительно кэширование данных в `array_view` объектов:  
  
-   Все хорошо синхронизированный доступ к `array` объекта и `array_view` объекта на нем в порядке программы подчиняются последовательный происходит-до связи.  
  
-   Хорошо синхронизированный доступ к перекрывающимся `array_view` объектов на же сочетания клавиш на отдельном `array` объекта используются псевдонимы через `array` объекта. Они вызывать всего происходит-перед отношение, которое подчиняется порядка в программе. Не выполняется кэширование. Если `array_view` объекты выполняются на различные сочетания клавиш, порядок доступа не определен, создание состояние гонки.  
  
 При создании `array_view` объекта с помощью указателя в системной памяти, необходимо изменить представление `array_view` только с использованием объекта `array_view` указателя. Кроме того, необходимо вызвать метод `refresh()` на одном из `array_view` объектов, подключенные к системе указатель, базовых внутренней памяти при изменении напрямую, а не через `array_view` объекта.  
  
 В обоих случаях уведомляет `array_view` объекта изменении базовых внутренней памяти и что все копии, которые находятся на ускорителе устарели. Если следовать рекомендациям представления на основе указателя идентичны для представления данных параллельного массивов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="dtor"></a>~ array_view 

 Уничтожает `array_view` объекта.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="ctor"></a>array_view 

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
 `_Arr_type`  
 Тип элементов массива C-стиле, из которого данные предоставляются.  
  
 `_Container`  
 Аргумент шаблона, который необходимо указать линейной контейнер, который поддерживает `data()` и `size()` члены.  
  
 `_E0`  
 Наиболее значимые компонент экстента в этом разделе.  
  
 `_E1`  
 Далее к старший значащий компонент экстента в этом разделе.  
  
 `_E2`  
 Наименее значащие компонент экстента в этом разделе.  
  
 `_Extent`  
 Экстент в каждой размерности `array_view`.  
  
 `_Other`  
 Объект типа `array_view<T,N>` для инициализации нового `array_view`.  
  
 `_Size`  
 Размер массива C-стиле, из которого данные предоставляются.  
  
 `_Src`  
 Указатель на исходные данные, которые будут скопированы в новый массив.  
  
##  <a name="copy_to"></a>copy_to 

 Копирует содержимое `array_view` в указанный целевой объект путем вызова `copy(*this, dest)`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Объект для копирования.  
  
##  <a name="data"></a>данные 

 Возвращает указатель на необработанные данные `array_view`.  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные `array_view`.  
  
##  <a name="discard_data"></a>discard_data 

 Удаляет текущий базовые данные этого представления. Это указание по оптимизации для среды выполнения, которая используется, чтобы избежать копирования содержимого текущего представления с целевым объектом `accelerator_view` , при доступе к, и его использование рекомендуется, если существующее содержимое не требуется. Этот метод является холостой в контексте restrict(amp)  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="extent"></a>экстент 

 Получает объект `extent`, который определяет форму объекта `array_view`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="get_extent"></a>get_extent 

 Возвращает [экстент](extent-class.md) объекта `array_view` объекта.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `extent` Объекта `array_view` объекта  
  
##  <a name="get_ref"></a>get_ref 

 Получите ссылку на элемент с _Index индексом. В отличие от других индексирования операторов для доступа к array_view на ЦП этот метод не выполняет синхронизацию неявно содержимое этого array_view к ЦП. После доступа к array_view в удаленном расположении или выполнение операции копирования, включающие этот array_view пользователи ответственны явно синхронизировать array_view к ЦП перед вызовом этого метода. Невыполнение этого требования приведет к неопределенному поведению.  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на элемент проиндексирован _Index  
  
##  <a name="get_source_accelerator_view"></a>get_source_accelerator_view 

 Возвращает accelerator_view, где находится источник данных array_view. Если array_view не имеет источника данных, этот API выдает runtime_exception  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="operator_call"></a>Operator() 

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
 `_Index`  
 Расположение элемента.  
  
 `_I0`  
 Индекс в первом измерении.  
  
 `_I1`  
 Индекс второго измерения.  
  
 `_I2`  
 Индекс в третьем измерении.  
  
 `_I`  
 Расположение элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента, который задается параметром или параметрами.  
  
##  <a name="operator_at"></a>оператор] 

 Возвращает элемент, указанный параметрами.  
  
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
 Значение элемента по индексу или `array_view` проецируется на старшем измерения.  
  
##  <a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного `array_view` этого объекта.  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `array_view` Объект для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `array_view` объекта.  
  
##  <a name="rank"></a>Ранг 

 Сохраняет ранг объекта `array_view` объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="refresh"></a>обновления 

 Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейса. Вызов этого метода отображает все данные из кэша устаревшим.  
  
```  
void refresh() const restrict(cpu);
```  
## <a name="reinterpret_as"></a>reinterpret_as 

Повторно интерпретирует array_view через одномерный array_view, имеющих в качестве альтернативы можно тип отличается от array_view источника.  
  
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
 `_Value_type2`  
 Тип данных нового `array_view` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `array_view` Объекта или const `array_view` , основанный на этом `array_view`, с типом элемента, преобразованные из `T` для `_Value_type2`, и сократить ранг с *N* значение 1.  
  
### <a name="remarks"></a>Примечания  
 Иногда бывает удобно просматривать многомерный массив в виде — линейной одномерный массив, который может иметь тип отличается от исходного массива. Это можно выполнить на `array_view` с помощью этого метода.  
  
**Предупреждение** Reinterpeting array_view объекта с помощью другого значения типа является потенциально небезопасные операции. Эту функцию следует использовать с осторожностью.  
  
 Ниже приведен пример:  
  
```cpp  
struct RGB { float r; float g; float b; };  
  
array<RGB,3>  a = ...;   
array_view<float,1> v = a.reinterpret_as<float>();   
  
assert(v.extent == 3*a.extent);  
```  
    
##  <a name="section"></a>раздел 

 Возвращает подраздел `array_view` объект, находящийся в указанный источник и, возможно, который имеет указанную область.  
  
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
 Ранг разделе.  
  
 `_Section_extent`  
 [Экстент](extent-class.md) объекта, который задает область, в разделе.  
  
 `_Section_origin`  
 [Индекс](index-class.md) объект, который указывает расположение начала координат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подраздел `array_view` объект, находящийся в указанный источник и, возможно, который имеет указанную область. Только если `index` объект указан, подраздел содержит все элементы связанного экстента, имеют индексы, размер которых превышает индексы элементов в `index` объекта.  
  
##  <a name="source_accelerator_view"></a>source_accelerator_view 

 Получает источник accelerator_view, связанный с этой array_view.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="synchronize"></a>синхронизировать 

 Синхронизирует все изменения, внесенные в `array_view` объекта обратно в исходные данные.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Access_type`  
 Будущей [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом сервере [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.  
  
##  <a name="synchronize_async"></a>synchronize_async 

 Асинхронно синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Access_type`  
 Будущей [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом сервере [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее, на которой будет ожидать завершения операции.  
  
##  <a name="synchronize_to"></a>synchronize_to 

 Синхронизирует все изменения, внесенные в этот array_view для указанного accelerator_view.  
  
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
  
##  <a name="synchronize_to_async"></a>synchronize_to_async 

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
  
##  <a name="value_type"></a>value_type 

 Тип значения array_view и связанный массив.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="view_as"></a>view_as 

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
 Тип данных элементов в исходные [массива](array-class.md) объекта и возвращаемый `array_view` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `array_view` Объект, который создается.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

