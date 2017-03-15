---
title: "Класс texture_view | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
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
ms.openlocfilehash: 7d3206aea6a6f1e3033e157b3b99a6b3486cb2ac
ms.lasthandoff: 02/24/2017

---
# <a name="textureview-class"></a>Класс texture_view
Предоставляет доступ на чтение и запись для текстуры. `texture_view`может использоваться только для чтения текстуры с типом значения `int`, `unsigned int`, или `float` , имеющие bpse 32-разрядная версия по умолчанию. Для чтения других форматов текстур, используйте `texture_view<const value_type, _Rank>`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class texture_view : public details::_Texture_base<value_type, _Rank>;  
 
template <
    typename value_type,  
    int _Rank  
>  
class texture_view<const value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
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
|`value_type`|Тип элементов в агрегатах текстуры.|  
|`coordinates_type`|Тип координат, используемый для указания текселя в `texture_view`— то есть, `short_vector` , имеет тот же ранг, как связанные текстуры, которая имеет тип значения `float`.|  
|`gather_return_type`|Возвращаемый тип, используемый для сбора операций — то есть 4 ранга `short_vector` , содержит четыре компонента Однородный цвет собираются из четырех значений текселя выборки.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор texture_view](#ctor)|Перегружен. Создает `texture_view` экземпляра.|  
|[~ texture_view деструктор](#ctor)|Уничтожает `texture_view` экземпляра.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод gather_alpha](#gather_alpha)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты альфа (w).|  
|[Метод gather_blue](#gather_blue)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты синего цвета (z).|  
|[Метод gather_green](#gather_green)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты зеленого (y).|  
|[Метод gather_red](#gather_red)|Перегружен. Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты красный (x).|  
|[GET-метод](#get)|Перегружен. Возвращает значение элемента по индексу.|  
|[Пример метода](#sample)|Перегружен. Примеры текстуру по указанным координатам и уровень детализации с помощью выборки указанной конфигурации.|  
|[Метод Set](#set)|Задает значение элемента по индексу.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор Operator()](#operator__)|Перегружен. Возвращает значение элемента по индексу.|  
|[Оператор Operator]](#operator_at)|Перегружен. Возвращает значение элемента по индексу.|  
|[оператор =-оператор](#operator_eq)|Перегружен. Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[value_type элемент данных](#value_type)|Тип значения элементов `texture_view`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `_Texture_base`  
  
 `texture_view`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен:** concurrency::graphics  
  
##  <a name="a-namedtora-textureview"></a><a name="dtor"></a>~ texture_view 

 Уничтожает `texture_view` экземпляра.  
  
```  
~texture_view() restrict(amp, cpu);
```  
  
##  <a name="a-namectora-textureview"></a><a name="ctor"></a>texture_view 

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
 `texture` На котором доступный `texture_view` создается.  
  
 [3, 4] Конструктор  
 `texture` На котором недоступному `texture_view` создается.  
  
 `_Other`  
 [5] конструктор копий  
 Для записи источника `texture_view`.  
  
 [6, 7] Конструктор копии  
 Недоступный источник `texture_view`.  
  
 `_Mipmap_level`  
 На уровне конкретного MIP-карты на источник `texture` этом, записываемые `texture_view` привязывает к. Значение по умолчанию — 0, представляющее уровень mip верхнего уровня (самый подробный).  
  
 `_Most_detailed_mip`  
 Верхнего уровня mip уровень (самый подробный) для представления относительно указанного `texture_view` объекта.  
  
 `_Mip_levels`  
 Количество уровней MIP-карты через `texture_view`.  
  
##  <a name="a-namegatherreda-gatherred"></a><a name="gather_red"></a>gather_red 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты красный (x).  
  
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
 Режим адресации для использования в образце `texture_view`. Режим адресации одинаков для всех измерений.  
  
 `_Sampler`  
 Образец настройки для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образец из вступили в силу. Дробные значения координат используются для интерполяции текселя образца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 4 ранга короткого вектора, содержащего компонент красный (x) 4 выборки текселя значения.  
  
##  <a name="a-namegathergreena-gathergreen"></a><a name="gather_green"></a>gather_green 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты зеленого (y).  
  
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
 Режим адресации для использования в образце `texture_view`. Режим адресации одинаков для всех измерений.  
  
 `_Sampler`  
 Образец настройки для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образец из вступили в силу. Дробные значения координат используются для интерполяции текселя образца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 4 ранга короткого вектора, содержащего компонент зеленый (y) 4 выборки текселя значения.  
  
##  <a name="a-namegatherbluea-gatherblue"></a><a name="gather_blue"></a>gather_blue 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты синего цвета (z).  
  
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
 Режим адресации для использования в образце `texture_view`. Режим адресации одинаков для всех измерений.  
  
 `_Sampler`  
 Образец настройки для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образец из вступили в силу. Дробные значения координат используются для интерполяции текселя образца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 4 ранга короткого вектора, содержащего компонент красный (x) 4 выборки текселя значения.  
  
##  <a name="a-namegatheralphaa-gatheralpha"></a><a name="gather_alpha"></a>gather_alpha 

 Примеры по указанным координатам текстуры с помощью конфигурации указанной выборки и возвращает четыре текселя выбранные компоненты альфа (w).  
  
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
 Режим адресации для использования в образце `texture_view`. Режим адресации одинаков для всех измерений.  
  
 `_Sampler`  
 Образец настройки для использования в образце `texture_view`.  
  
 `_Coord`  
 Координаты образец из вступили в силу. Дробные значения координат используются для интерполяции текселя образца.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ранг 4 короткий vector, содержащий альфа-канал (w) компонент 4 измеренных значений текселя.  
  
##  <a name="a-namegeta-get"></a><a name="get"></a>Получить 

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
 Уровень MIP-карт, из которого следует получить значение. Значение по умолчанию 0 представляет самый подробный уровень MIP-карты.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>оператор = 

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
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>оператор] 

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
 Одномерный индекс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента с индексом `_Index`.  
  
##  <a name="a-nameoperatora-operator"></a><a name="operator__"></a>Operator() 

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
 Наиболее значимый компонент индекса.  
  
 `_I1`  
 Далее к значащий компонент индекса.  
  
 `_I2`  
 Наименее значимый компонент индекса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение элемента с индексом `_Index`.  
  
##  <a name="a-namesamplea-sample"></a><a name="sample"></a>Образец 

 Примеры текстуру по указанным координатам и уровень детализации с помощью выборки указанной конфигурации.  
  
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
 Режим фильтрации для образца texture_view. Режим фильтрации одинаков для минимизации, максимизации и MIP-карты фильтры.  
  
 `_Address_mode`  
 Режим адрес, используемый для выборки texture_view. Режим адресации одинаков для всех измерений.  
  
 `_Sampler`  
 Образец настройки для использования в выборку texture_view.  
  
 `_Coord`  
 Координаты образец из вступили в силу. Дробные значения координат используются для интерполяции между значениями текселя.  
  
 `_Level_of_detail`  
 Значение задает уровень MIP-карты для выборки из. Дробные значения используются для интерполяции двух уровней MIP-карты. Уровень детализации по умолчанию — 0, представляющее самый подробный уровень mip.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Образец интерполированное значение.  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>набор 

 Задает значение элемента по указанному индексу в указанное значение.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Index`  
 Индекс элемента, возможно многомерным.  
  
 `value`  
 Значение, значение элемента.  
  
##  <a name="a-namevaluetypea-valuetype"></a><a name="value_type"></a>value_type 

 Тип значения элементов texture_view.  
  
```  
typedef typename const value_type value_type;  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)

