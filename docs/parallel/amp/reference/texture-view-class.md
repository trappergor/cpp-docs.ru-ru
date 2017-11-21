---
title: "Класс texture_view | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- texture_view
- AMP_GRAPHICS/texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::texture_view
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_alpha
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_blue
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_green
- AMP_GRAPHICS/Concurrency::graphics::texture_view::gather_red
- AMP_GRAPHICS/Concurrency::graphics::texture_view::get
- AMP_GRAPHICS/Concurrency::graphics::texture_view::sample
- AMP_GRAPHICS/Concurrency::graphics::texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::texture_view::value_type
dev_langs: C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d03b67b1207827ae753c9d2583d57eab49dc223a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="textureview-class"></a>Класс texture_view
Предоставляет доступ на чтение и запись для текстуры. `texture_view`может использоваться только для чтения текстуры, тип которого значение является `int`, `unsigned int`, или `float` , имеющие bpse 32-разрядных по умолчанию. Для чтения других форматов текстур, используйте `texture_view<const value_type, _Rank>`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename value_type,int _Rank>  
class texture_view;  
 
template<typename value_type, int _Rank>  
class texture_view 
   : public details::_Texture_base<value_type, _Rank>;  
 
template<typename value_type, int _Rank>  
class texture_view<const value_type, _Rank> 
   : public details::_Texture_base<value_type, _Rank>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `value_type`  
 Тип элементов в совокупности текстуры.  
  
 `_Rank`  
 Ранг `texture_view`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`value_type`|Тип элементов в статистических выражениях текстуры.|  
|`coordinates_type`|Тип координат, используется для указания текселя в `texture_view`— то есть `short_vector` , имеет тот же ранг, как связанные текстуры, которая имеет тип значения `float`.|  
|`gather_return_type`|Тип возвращаемого значения, используемые для сбора операций — то есть ранг 4 `short_vector` содержит четыре компонента Однородный цвет полученные четыре значения текселя выборки.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор texture_view](#ctor)|Перегружен. Создает `texture_view` экземпляра.|  
|[~ texture_view деструктор](#ctor)|Уничтожает `texture_view` экземпляра.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[gather_alpha](#gather_alpha)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компоненты альфа (w).|  
|[gather_blue](#gather_blue)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компоненты синего цвета (z).|  
|[gather_green](#gather_green)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компоненты зеленого цвета (y).|  
|[gather_red](#gather_red)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компонентов красного цвета (x).|  
|[get](#get)|Перегружен. Возвращает значение элемента по индексу.|  
|[Пример](#sample)|Перегружен. Образцы текстуру по указанным координатам и уровень детализации с помощью выборки указанной конфигурации.|  
|[set](#set)|Задает значение элемента по индексу.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Operator()](#operator_call)|Перегружен. Возвращает значение элемента по индексу.|  
|[оператор]](#operator_at)|Перегружен. Возвращает значение элемента по индексу.|  
|[operator=](#operator_eq)|Перегружен. Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[value_type](#value_type)|Тип значения элементов `texture_view`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Texture_base`  
  
 `texture_view`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен:** concurrency::graphics  
  
##  <a name="dtor"></a>~ texture_view 

 Уничтожает `texture_view` экземпляра.  
  
```  
~texture_view() restrict(amp, cpu);
```  
  
##  <a name="ctor"></a>texture_view 

 Создает `texture_view` экземпляра.  
  
```  
texture_view(// [1] constructor  
    texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [2] constructor  
    texture<value_type, _Rank>& _Src,  
    unsigned int _Mipmap_level = 0) restrict(cpu);

 
texture_view(// [3] constructor  
    const texture<value_type, _Rank>& _Src) restrict(amp);

 
texture_view(// [4] constructor  
    const texture<value_type, _Rank>& _Src,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);

 
texture_view(// [5] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [6] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view(// [7] copy constructor  
    const texture_view<const value_type, _Rank>& _Other,  
    unsigned int _Most_detailed_mip,  
    unsigned int _Mip_levels) restrict(cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Src`  
 [1, 2] Конструктор  
 `texture` На котором для записи `texture_view` создается.  
  
 [3, 4] Конструктор  
 `texture` Выступающей недоступному `texture_view` создается.  
  
 `_Other`  
 [5] конструктор копий  
 Источник для записи `texture_view`.  
  
 [6, 7] Конструктор копии  
 Источник не поддерживает записи `texture_view`.  
  
 `_Mipmap_level`  
 На уровне конкретного MIP-карты на источнике `texture` то этом поддерживает возможность перезаписи `texture_view` привязывает. Значение по умолчанию — 0, представляющее уровень mip верхнего уровня (наибольшая детализация).  
  
 `_Most_detailed_mip`  
 Верхнего уровня mip уровень (наибольшая детализация) для представления относительно указанного `texture_view` объекта.  
  
 `_Mip_levels`  
 Количество уровней MIP-карты, доступны через `texture_view`.  
  
##  <a name="gather_red"></a>gather_red 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компонентов красного цвета (x).  
  
```  
const gather_return_type gather_red(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_red(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Address_mode`  
 Режим адрес, используемый для образца `texture_view`. Режим адресации одинаково для всех измерений.  
  
 `_Sampler`  
 Образец конфигурации для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образца из вступили в силу. Дробные значения координат используются для интерполяции образец текселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 4 ранга короткого вектора, содержащего компонент красного цвета (x), 4, выбранных значений текселя.  
  
##  <a name="gather_green"></a>gather_green 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компоненты зеленого цвета (y).  
  
```  
const gather_return_type gather_green(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_green(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Address_mode`  
 Режим адрес, используемый для образца `texture_view`. Режим адресации одинаково для всех измерений.  
  
 `_Sampler`  
 Образец конфигурации для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образца из вступили в силу. Дробные значения координат используются для интерполяции образец текселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 4 ранга короткого вектора, содержащего компонент зеленого цвета (y), 4, выбранных значений текселя.  
  
##  <a name="gather_blue"></a>gather_blue 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компоненты синего цвета (z).  
  
```  
const gather_return_type gather_blue(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_blue(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Address_mode`  
 Режим адрес, используемый для образца `texture_view`. Режим адресации одинаково для всех измерений.  
  
 `_Sampler`  
 Образец конфигурации для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образца из вступили в силу. Дробные значения координат используются для интерполяции образец текселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 4 ранга короткого вектора, содержащего компонент красного цвета (x), 4, выбранных значений текселя.  
  
##  <a name="gather_alpha"></a>gather_alpha 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре выборки текселя компоненты альфа (w).  
  
```  
const gather_return_type gather_alpha(
    const sampler& _Sampler,  
    const coordinates_type& _Coord) const restrict(amp);

 
template<
    address_mode _Address_mode = address_clamp  
>  
const gather_return_type gather_alpha(
    const coordinates_type& _Coord) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Address_mode`  
 Режим адрес, используемый для образца `texture_view`. Режим адресации одинаково для всех измерений.  
  
 `_Sampler`  
 Образец конфигурации для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образца из вступили в силу. Дробные значения координат используются для интерполяции образец текселя.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ранг 4 короткий vector, содержащий (w) компонент 4 выборки текселя значения альфа-канал.  
  
##  <a name="get"></a>Получить 

 Возвращает значение элемента по указанному индексу.  
  
```  
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

 
value_type get(
    const index<_Rank>& _Index,  
    unsigned int _Mip_level = 0) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента, который требуется получить, возможно многомерным.  
  
 `_Mip_level`  
 Уровень MIP-карт, из которого следует получать значение. Значение по умолчанию 0 представляет наиболее подробный уровень MIP-карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента.  
  
##  <a name="operator_eq"></a>оператор = 

 Назначает представление текстуры же как и в заданном `texture_view` к этому `texture_view` экземпляра.  
  
```  
texture_view<value_type, _Rank>& operator= (// [1] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

 
texture_view<const value_type, _Rank>& operator= (// [2] copy constructor  
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

 
texture_view<const value_type, _Rank>& operator= (// [3] copy constructor  
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 [1, 2] Конструктор копии  
 Доступный для записи `texture_view` объекта.  
  
 [3] конструктор копий  
 Не поддерживает записи `texture_view` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `texture_view` экземпляра.  
  
##  <a name="operator_at"></a>оператор] 

 Возвращает значение элемента по индексу.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);

 
value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс, возможно многомерным.  
  
 `_I0`  
 Одномерный массив индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента с индексом `_Index`.  
  
##  <a name="operator_call"></a>Operator() 

 Возвращает значение элемента по индексу.  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,   int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);

 
value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
value_type operator() (
    int _I0) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс, возможно многомерным.  
  
 `_I0`  
 Старший значащий компонент индекса.  
  
 `_I1`  
 Далее к старший значащий компонент индекса.  
  
 `_I2`  
 Компонент наименьшего индекса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента с индексом `_Index`.  
  
##  <a name="sample"></a>Пример 

 Образцы текстуру по указанным координатам и уровень детализации с помощью выборки указанной конфигурации.  
  
```  
value_type sample(
    const sampler& _Sampler,  
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);

 
template<
    filter_mode _Filter_mode = filter_linear,  
    address_mode _Address_mode = address_clamp  
>  
value_type sample(
    const coordinates_type& _Coord,  
    float _Level_of_detail = 0.0f) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter_mode`  
 Режим фильтрации, используемый для выборки, texture_view. Режим фильтрации является одинаковым для минимизация, максимизации ожидания и фильтры MIP-карты.  
  
 `_Address_mode`  
 Режим адрес, используемый для выборки texture_view. Режим адресации одинаково для всех измерений.  
  
 `_Sampler`  
 Конфигурация пробы для выборки texture_view.  
  
 `_Coord`  
 Координаты образца из вступили в силу. Дробные значения координат позволяют выполнять интерполяцию между значениями текселя.  
  
 `_Level_of_detail`  
 Значение задает уровень MIP-карты для выборки из. Дробные значения позволяют выполнять интерполяцию между двумя уровнями MIP-карты. Уровень детализации по умолчанию — 0, представляющее наиболее подробный уровень mip.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Образец интерполированное значение.  
  
##  <a name="set"></a>набор 

 Задает значение элемента по указанному индексу в указанное значение.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс задаваемого элемента, возможно многомерным.  
  
 `value`  
 Значение, значение элемента.  
  
##  <a name="value_type"></a>value_type 

 Тип значения элементов texture_view.  
  
```  
typedef typename const value_type value_type;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
