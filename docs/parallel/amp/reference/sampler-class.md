---
title: Класс sampler | Документы Microsoft
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7261a28f5dea4a8de4af3c169f9b67537e5f3088
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121855"
---
# <a name="sampler-class"></a>Класс sampler

Класс пробы агрегирует данные конфигурации выборки, используемый для дискретизации текстур.

## <a name="syntax"></a>Синтаксис

```cpp
class sampler;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Образец конструктора](#ctor)|Перегружен. Создает экземпляр образца.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Возвращает `address_mode` , связанную с объектом пробы.|
|[get_border_color](#get_border_color)|Возвращает цвет границы, связанный с объектом пробы.|
|[get_filter_mode](#get_filter_mode)|Возвращает `filter_mode` , связанную с объектом пробы.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[оператор=](#operator_eq)|Перегружен. Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[address_mode](#address_mode)|Возвращает режим адрес `sampler` объекта.|
|[border_color](#border_color)|Возвращает цвет границы `sampler` объекта.|
|[filter_mode](#filter_mode)|Возвращает режим фильтра `sampler` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`sampler`

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** concurrency::graphics

##  <a name="ctor"></a> Образец

Создает экземпляр класса [класс sampler](sampler-class.md).

```cpp
sampler() restrict(cpu);    // [1] default constructor

sampler(                    // [2] constructor
    filter_mode _Filter_mode) restrict(cpu);


sampler(                    // [3] constructor
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);


sampler(                    // [4] constructor
    filter_mode _Filter_mode,
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);


sampler(                    // [5] copy constructor
    const sampler& _Other) restrict(amp,
    cpu);


sampler(                    // [6] move constructor
    sampler&& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Параметры

*_Filter_mode*  
 Режим фильтрации, используемый в выборки.

*_Address_mode*  
 Режим адресации для использования в выборки для всех измерений.

*_Border_color*  
 Цвет границы для использования при address_border режим адресации. Значение по умолчанию — `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.

*_Other*  
[5] конструктор копий  
`sampler` Объект для копирования в новый `sampler` экземпляра.

[6] конструктор перемещения  
`sampler` Объекта, чтобы переместить в новый `sampler` экземпляра.

##  <a name="address_mode"></a> address_mode

Возвращает режим адрес `sampler` объекта.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

##  <a name="border_color"></a> border_color

Возвращает цвет границы `sampler` объекта.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

##  <a name="filter_mode"></a> filter_mode

Возвращает режим фильтра `sampler` объекта.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

##  <a name="get_address_mode"></a> get_address_mode

Возвращает режим фильтра, настроенный для этого `sampler`.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Возвращаемое значение

Режим адрес, настроенный для образцом.

##  <a name="get_border_color"></a> get_border_color

Возвращает цвет границы, настроенный для этого `sampler`.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Float_4, содержащий цвет границы.

##  <a name="get_filter_mode"></a> get_filter_mode

Возвращает режим фильтра, настроенный для этого `sampler`.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Режим фильтра, настроенный для образцом.

##  <a name="operator_eq"></a> оператор =

Присваивает значение другого объекта пробы существующей пробы.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator 
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Other*  
[1] оператор присваивания копированием  
`sampler` Объект для копирования в этот `sampler`.

[2] оператор присваивания перемещения  
`sampler` Объектов для перемещения в это `sampler`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот экземпляр образца.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)  
