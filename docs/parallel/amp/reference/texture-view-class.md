---
title: Класс texture_view | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8a87c303d4527f89a7d7f59b69b3cc8572e0e7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387411"
---
# <a name="textureview-class"></a>Класс texture_view

Предоставляет доступ на чтение и запись к текстуре. `texture_view` может использоваться только для чтения текстур, тип значений которых — `int`, `unsigned int`, или `float` , имеющих 32-разрядных bpse по умолчанию. Для чтения других форматов текстур используйте `texture_view<const value_type, _Rank>`.

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

*value_type*<br/>
Тип элементов в агрегате текстур.

*_Rank*<br/>
Ранг `texture_view`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`value_type`|Тип элементов в агрегатах текстур.|
|`coordinates_type`|Тип координаты, используемой для определения текселя в `texture_view`— то есть `short_vector` , имеет один и тот же ранг, связанной текстурой, имеющий тип значения `float`.|
|`gather_return_type`|Возвращаемый тип, используемый для сбора операция — то есть, ранжирование 4 `short_vector` что содержит 4 однородных компонента цвета собранные от 4 попробованных значений texel.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор texture_view](#ctor)|Перегружен. Создает `texture_view` экземпляра.|
|[~ texture_view деструктор](#ctor)|Уничтожает `texture_view` экземпляра.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[gather_alpha](#gather_alpha)|Перегружен. Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает альфа (w) компоненты четыре текселей.|
|[gather_blue](#gather_blue)|Перегружен. Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает четыре текселей компоненты синего цвета (z).|
|[gather_green](#gather_green)|Перегружен. Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает четыре текселей компонентов зеленого цвета (y).|
|[gather_red](#gather_red)|Перегружен. Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает четыре текселей компонентов красного цвета (x).|
|[get](#get)|Перегружен. Получает значение элемента по индексу.|
|[Пример](#sample)|Перегружен. Выборку текстуры в заданных координатах и уровень детализации с помощью определенной конфигурации выборки.|
|[set](#set)|Задает значение элемента по индексу.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Operator()](#operator_call)|Перегружен. Получает значение элемента по индексу.|
|[оператор]](#operator_at)|Перегружен. Получает значение элемента по индексу.|
|[оператор=](#operator_eq)|Перегружен. Оператор присвоения.|

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

##  <a name="dtor"></a> ~ texture_view

Уничтожает `texture_view` экземпляра.

```
~texture_view() restrict(amp, cpu);
```

##  <a name="ctor"></a> texture_view

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

*_Src*<br/>
[1, 2] Конструктор `texture` на котором незаписываемый `texture_view` создается.

[3, 4] Конструктор `texture` на котором незаписываемый `texture_view` создается.

*_Другое*<br/>
[5] конструктор копии источник с возможностью записи `texture_view`.

[6, 7] Копирующий конструктор недоступного для записи источник `texture_view`.

*_Mipmap_level*<br/>
Определенный уровень mipmap в источнике `texture` , это перезаписываемое `texture_view` привязывается к. Значение по умолчанию — 0, представляющее уровень mip верхнего уровня (наибольшая детализация).

*_Most_detailed_mip*<br/>
Верхнего уровня mip (наибольшая детализация) уровень представления, относительно указанного `texture_view` объекта.

*_Mip_levels*<br/>
Количество уровней mipmap доступных через `texture_view`.

##  <a name="gather_red"></a> gather_red

Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает четыре текселей компонентов красного цвета (x).

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

*_Address_mode*<br/>
Режим адреса, чтобы использовать пример `texture_view`. Режим адреса одинаков для всех измерений.

*_Sampler*<br/>
Конфигурация дискретизатора, используемая для примера `texture_view`.

*_Coord*<br/>
Координаты для берется образец. Для интерполяции между текселями выборки используются значения дробных координат.

### <a name="return-value"></a>Возвращаемое значение

Короткий вектор ранга 4, содержащий компонент красного цвета (x) 4 измеренных значений текселей.

##  <a name="gather_green"></a> gather_green

Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает четыре текселей компонентов зеленого цвета (y).

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

*_Address_mode*<br/>
Режим адреса, чтобы использовать пример `texture_view`. Режим адреса одинаков для всех измерений.

*_Sampler*<br/>
Конфигурация дискретизатора, используемая для примера `texture_view`.

*_Coord*<br/>
Координаты для берется образец. Для интерполяции между текселями выборки используются значения дробных координат.

### <a name="return-value"></a>Возвращаемое значение

Короткий вектор ранга 4, содержащий компонент зеленого цвета (y) 4 измеренных значений текселей.

##  <a name="gather_blue"></a> gather_blue

Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает четыре текселей компоненты синего цвета (z).

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

*_Address_mode*<br/>
Режим адреса, чтобы использовать пример `texture_view`. Режим адреса одинаков для всех измерений.

*_Sampler*<br/>
Конфигурация дискретизатора, используемая для примера `texture_view`.

*_Coord*<br/>
Координаты для берется образец. Для интерполяции между текселями выборки используются значения дробных координат.

### <a name="return-value"></a>Возвращаемое значение

Короткий вектор ранга 4, содержащий компонент красного цвета (x) 4 измеренных значений текселей.

##  <a name="gather_alpha"></a> gather_alpha

Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает альфа (w) компоненты четыре текселей.

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

*_Address_mode*<br/>
Режим адреса, чтобы использовать пример `texture_view`. Режим адреса одинаков для всех измерений.

*_Sampler*<br/>
Конфигурация дискретизатора, используемая для примера `texture_view`.

*_Coord*<br/>
Координаты для берется образец. Для интерполяции между текселями выборки используются значения дробных координат.

### <a name="return-value"></a>Возвращаемое значение

Короткий вектор ранга 4 содержащий альфа (w) компонент 4 измеренных значений текселей.

##  <a name="get"></a> Получить

Получает значение элемента по указанному индексу.

```
const value_type get(
    const index<_Rank>& _Index) const restrict(amp);

value_type get(
    const index<_Rank>& _Index,
    unsigned int _Mip_level = 0) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс элемента, который требуется получить, возможно многомерный.

*_Mip_level*<br/>
Уровень mipmap, из которого нужно получить значение. Значение по умолчанию 0 представляет самый подробный уровень MIP-карты.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента.

##  <a name="operator_eq"></a> оператор =

Присваивает представление той же текстуры, что и заданный `texture_view` к этому `texture_view` экземпляра.

```
texture_view<value_type, _Rank>& operator= (// [1] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(amp, cpu);

texture_view<const value_type, _Rank>& operator= (// [2] copy constructor
    const texture_view<value_type, _Rank>& _Other) restrict(cpu);

texture_view<const value_type, _Rank>& operator= (// [3] copy constructor
    const texture_view<const value_type, _Rank>& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
[1, 2] Конструктор копии для записи A `texture_view` объекта.

[3] конструктор копии A недоступного для записи `texture_view` объекта.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `texture_view` экземпляра.

##  <a name="operator_at"></a> оператор]

Возвращает значение элемента по индексу.

```
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);

value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс, возможно многомерный.

*_I0*<br/>
Одномерный индекс.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента с индексом `_Index`.

##  <a name="operator_call"></a> Operator()

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

*_Index*<br/>
Индекс, возможно многомерный.

*_I0*<br/>
Наиболее значимый компонент индекса.

*_I1*<br/>
Далее к наиболее значимый компонент индекса.

*_I2*<br/>
Наименее значимый компонент индекса.

### <a name="return-value"></a>Возвращаемое значение

Значение элемента с индексом `_Index`.

##  <a name="sample"></a> Пример

Выборку текстуры в заданных координатах и уровень детализации с помощью определенной конфигурации выборки.

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

*_Filter_mode*<br/>
Режим фильтра для использования в texture_view образца. Режим установки фильтра применяется одинаково для минимизации, максимизации и фильтров mipmap.

*_Address_mode*<br/>
Режим адреса для использования в texture_view образца. Режим адреса одинаков для всех измерений.

*_Sampler*<br/>
Конфигурация дискретизатора, используемая для дискретизации texture_view.

*_Coord*<br/>
Координаты для берется образец. Для интерполяции между значениями текселей используются значения дробных координат.

*_Level_of_detail*<br/>
Значение определяет уровень mipmap для выборки из. Для интерполяции между двумя уровнями MIP-карт используются значения дробных. Уровень детализации по умолчанию — 0, которое представляет самый подробный уровень mip.

### <a name="return-value"></a>Возвращаемое значение

Интерполированное значение выборки.

##  <a name="set"></a> Набор

Задает значение элемента по указанному индексу, указанному значению.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Index*<br/>
Индекс элемента, который требуется задать, возможно многомерный.

*значение*<br/>
Задаваемое значение элемента.

##  <a name="value_type"></a> value_type

Тип значения элементов texture_view.

```
typedef typename const value_type value_type;
```

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
