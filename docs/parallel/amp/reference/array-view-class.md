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
- amp/Concurrency::array_view
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: ec096dbcd485b9360d07d1b56511b13c13d1b4cf
ms.lasthandoff: 02/24/2017

---
# <a name="arrayview-class"></a>Класс array_view
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
|[Конструктор array_view](#ctor)|Инициализирует новый экземпляр класса `array_view`. Нет конструктора по умолчанию для `array<T,N>`. Все конструкторы ограничены для запуска только в ЦП и не может быть выполнена на целевом Direct3D.|  
|[~ array_view деструктор](#ctor)|Уничтожает `array_view` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[copy_to метод](#copy_to)|Копирует содержимое `array_view` объект в указанное назначение путем вызова `copy(*this, dest)`.|  
|[Метод данных](#data)|Возвращает указатель на необработанные данные `array_view`.|  
|[Метод discard_data](#discard_data)|Удаляет текущий базовые данные этого представления.|  
|[get_extent метод](#get_extent)|Возвращает объект экстента array_view объекта.|  
|[Метод get_ref](#get_ref)|Возвращает ссылку на индексированного элемента.|  
|[Метод get_source_accelerator_view](#get_source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) где источник данных `array_view` находится.|  
|[Метод обновления](#refresh)|Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейса. Вызов этого метода отображает все кэшированные данные устаревшим.|  
|[reinterpret_as метод](#reinterpret_as)|Возвращает одномерный массив, содержащий все элементы в `array_view` объекта.|  
|[раздел метод](#section)|Возвращает подраздел `array_view` объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область.|  
|[Метод синхронизации](#synchronize)|Синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.|  
|[Метод synchronize_async](#synchronize_async)|Асинхронно синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.|  
|[Метод synchronize_to](#synchronize_to)|Синхронизирует любые изменения, внесенные в `array_view` объекта на указанное [accelerator_view](accelerator-view-class.md).|  
|[Метод synchronize_to_async](#synchronize_to_async)|Асинхронно синхронизирует любые изменения, внесенные в `array_view` объекта на указанное [accelerator_view](accelerator-view-class.md).|  
|[view_as метод](#view_as)|Создает `array_view` объектов с помощью другого ранга `array_view` данных объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор Operator()](#operator_call)|Возвращает значение элемента, который определяется один или несколько параметров.|  
|[Оператор Operator]](#operator_at)|Возвращает элемент, указанный в параметрах.|  
|[оператор =-оператор](#operator_eq)|Копирует содержимое указанного `array_view` объекта в другой.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ранг константа](#rank)|Сохраняет ранг объекта `array_view` объекта.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[экстент элемент данных](#extent)|Получает объект `extent`, который определяет форму объекта `array_view`.|  
|[source_accelerator_view элемент данных](#source_accelerator_view)|Возвращает [accelerator_view](accelerator-view-class.md) где источник данных `array_view` находится|  
|[value_type элемент данных](#value_type)|Тип значения `array_view` и связанного массива.|  
  
## <a name="remarks"></a>Примечания  
 `array_view` Класс представляет представление данных, которое содержится в [массива](array-class.md) объекта или подраздел `array` объекта.  
  
 Можно получить доступ к `array_view` объекта, где источник данных расположен (локально) или на различных сочетаний клавиш или домен согласованности (удаленно). Когда доступ к объекту удаленно, представления копируются и кэшируются при необходимости. За исключением эффекты автоматического кэширования `array_view` объекты имеют показатели производительности, аналогичен `array` объектов. При небольших производительности доступа к данным через представления.  
  
 Существует три варианта пульт дистанционного управления:  
  
-   Представление указателя памяти системы передается с помощью параметра [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) вызов ускоритель и доступ осуществляется через сочетания клавиш.  
  
-   Представление в массив, расположенных на ускоритель передается с помощью параметра `parallel_for_each` вызов другого сочетаний клавиш и осуществляется.  
  
-   Представление в массив, расположенных на ускоритель осуществляется на ЦП.  
  
 В любом из этих сценариев, упоминаемого представления копируются средой выполнения в удаленном расположении и, если изменен на вызовы `array_view` объекта, копируются обратно в локальное расположение. Среда выполнения может оптимизировать процесс копирования изменений обратно, может копировать только измененные элементы или может также скопируйте фрагменты без изменений. Перекрывающиеся `array_view` объектов в одном источнике данных не гарантируется для поддержания целостности данных в удаленном расположении.  
  
 Необходимо синхронизировать многопоточного доступа к тому же источнику данных.  
  
 Среда выполнения предоставляет следующие гарантии относительно кэширование данных в `array_view` объектов:  
  
-   Все хорошо синхронизированный доступ к `array` объекта и `array_view` объекта на нем в порядке программы подчиняются последовательное происходит-перед связь.  
  
-   Хорошо синхронизированных доступ к перекрывающимся `array_view` объектов на же сочетания клавиш на одном `array` объекта используются псевдонимы через `array` объекта. Они вызывать всего происходит-перед отношение, которое подчиняется порядка в программе. Не выполняется кэширование. Если `array_view` объекты выполняются на разных ускорители, порядок доступа не определен, создание состояние гонки.  
  
 При создании `array_view` объекта с помощью указателя в системной памяти, необходимо изменить представление `array_view` только с помощью объекта `array_view` указателя. Кроме того, необходимо вызвать `refresh()` на одном из `array_view` объектов, присоединенных к указателю системы базовой внутренней памяти при изменении напрямую, а не через `array_view` объекта.  
  
 В обоих случаях сообщает `array_view` объекта изменении базовых внутренней памяти и что все копии, которые находятся в ускоритель устарели. Если следовать рекомендациям представления на основе указателя идентичны для представления данных параллельными массивами.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
##  <a name="a-namedtora-arrayview"></a><a name="dtor"></a>~ array_view 

 Уничтожает `array_view` объекта.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="a-namectora-arrayview"></a><a name="ctor"></a>array_view 

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
 Тип элементов массива C-стиль, из которой данные передаются.  
  
 `_Container`  
 Аргумент шаблона, который необходимо указать линейной контейнера, поддерживающего `data()` и `size()` члены.  
  
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
  
##  <a name="a-namecopytoa-copyto"></a><a name="copy_to"></a>copy_to 

 Копирует содержимое `array_view` в указанный конечный объект, вызвав `copy(*this, dest)`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Параметры  
 `_Dest`  
 Объект для копирования.  
  
##  <a name="a-namedataa-data"></a><a name="data"></a>данные 

 Возвращает указатель на необработанные данные `array_view`.  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на необработанные данные `array_view`.  
  
##  <a name="a-namediscarddataa-discarddata"></a><a name="discard_data"></a>discard_data 

 Удаляет текущий базовые данные этого представления. Это позволяет избежать копирования текущее содержимое представления в целевой среде выполнения указание по оптимизации `accelerator_view` , при доступе к, и его использование рекомендуется, если нет необходимости существующего содержимого. Этот метод является холостой при использовании в контексте restrict(amp)  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="a-nameextenta-extent"></a><a name="extent"></a>экстент 

 Получает объект `extent`, который определяет форму объекта `array_view`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namegetextenta-getextent"></a><a name="get_extent"></a>get_extent 

 Возвращает [экстент](extent-class.md) объекта `array_view` объекта.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `extent` Объекта `array_view` объекта  
  
##  <a name="a-namegetrefa-getref"></a><a name="get_ref"></a>get_ref 

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
  
##  <a name="a-namegetsourceacceleratorviewa-getsourceacceleratorview"></a><a name="get_source_accelerator_view"></a>get_source_accelerator_view 

 Возвращает accelerator_view, где находится источник данных array_view. Если array_view имеет источник данных, этот интерфейс API вызывает runtime_exception  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="a-nameoperatorcalla-operator"></a><a name="operator_call"></a>Operator() 

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
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>оператор] 

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
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

 Копирует содержимое указанного `array_view` этого объекта.  
  
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
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>Ранг 

 Сохраняет ранг объекта `array_view` объекта.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namerefresha-refresh"></a><a name="refresh"></a>обновление 

 Уведомляет `array_view` объекта, привязанного памяти был изменен вне `array_view` интерфейса. Вызов этого метода отображает все кэшированные данные устаревшим.  
  
```  
void refresh() const restrict(cpu);
```  
## <a name="a-namereinterpretasa-reinterpretas"></a><a name="reinterpret_as"></a>reinterpret_as 

Повторно интерпретирует array_view через одномерный array_view, которой в качестве альтернативы может иметь тип другое значение, чем array_view источника.  
  
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
 `array_view` Объекта или const `array_view` объекта, который основан на это `array_view`, с типом элемента, преобразованное из `T` для `_Value_type2`, и сократить ранг с *N* 1.  
  
### <a name="remarks"></a>Примечания  
 Иногда бывает удобно просматривать многомерный массив — линейная одномерный массив, который может иметь тип отличается от исходного массива. Для этого на `array_view` с помощью этого метода.  
  
**Предупреждение** Reinterpeting array_view объекта с помощью другого значения типа является потенциально небезопасные операции. Эта функция должна использоваться с осторожностью.  
  
 Ниже приведен пример:  
  
```cpp  
struct RGB { float r; float g; float b; };  
  
array<RGB,3>  a = ...;   
array_view<float,1> v = a.reinterpret_as<float>();   
  
assert(v.extent == 3*a.extent);  
```  
    
##  <a name="a-namesectiona-section"></a><a name="section"></a>раздел 

 Возвращает подраздел `array_view` объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область.  
  
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
 [Экстент](extent-class.md) объекта, который задает область раздела. Источником является 0.  
  
 `_Idx`  
 [Индекс](index-class.md) объект, который указывает расположение начала координат. Подраздел является rest экстента.  
  
 `_I0`  
 Наиболее значимые компонент источника в этом разделе.  
  
 `_I1`  
 Далее к значащий компонент источника в этом разделе.  
  
 `_I2`  
 Младший компонент источника в этом разделе.  
  
 `_Rank`  
 Ранг раздела.  
  
 `_Section_extent`  
 [Экстент](extent-class.md) объекта, который задает область раздела.  
  
 `_Section_origin`  
 [Индекс](index-class.md) объект, который указывает расположение начала координат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Подраздел `array_view` объект, находящийся в указанный источник и, Дополнительно, который имеет указанную область. Только если `index` указан объект, подраздел содержит все элементы в экстенте связанные, имеют индексы, превышающие индексы элементов в `index` объекта.  
  
##  <a name="a-namesourceacceleratorviewa-sourceacceleratorview"></a><a name="source_accelerator_view"></a>source_accelerator_view 

 Возвращает источник accelerator_view, связанный с этой array_view.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="a-namesynchronizea-synchronize"></a><a name="synchronize"></a>синхронизировать 

 Синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Access_type`  
 Предполагаемого [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.  
  
##  <a name="a-namesynchronizeasynca-synchronizeasync"></a><a name="synchronize_async"></a>synchronize_async 

 Асинхронно синхронизирует любые изменения, внесенные в `array_view` объекта обратно в исходные данные.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Access_type`  
 Предполагаемого [access_type](concurrency-namespace-enums-amp.md#access_type) на целевом [accelerator_view](accelerator-view-class.md). Этот параметр имеет значение по умолчанию `access_type_read`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Будущее, на которой будет ожидать завершения операции.  
  
##  <a name="a-namesynchronizetoa-synchronizeto"></a><a name="synchronize_to"></a>synchronize_to 

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
  
##  <a name="a-namesynchronizetoasynca-synchronizetoasync"></a><a name="synchronize_to_async"></a>synchronize_to_async 

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
  
##  <a name="a-namevaluetypea-valuetype"></a><a name="value_type"></a>value_type 

 Тип значения array_view и связанного массива.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="a-nameviewasa-viewas"></a><a name="view_as"></a>view_as 

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
 `array_view` Объект.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

