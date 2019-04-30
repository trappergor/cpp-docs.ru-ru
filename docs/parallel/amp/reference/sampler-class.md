---
title: Класс sampler
ms.date: 06/28/2018
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
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
ms.openlocfilehash: 1a66e4d025a7592b78839dbe5f25f9103da41224
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352597"
---
# <a name="sampler-class"></a>Класс sampler

Класс образца вычисляет сведения о конфигурации выборки, используемый для дискретизации текстур.

## <a name="syntax"></a>Синтаксис

```cpp
class sampler;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Образец конструктор](#ctor)|Перегружен. Создает экземпляр дискретизатора.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Возвращает `address_mode` , связанную с объектом образца.|
|[get_border_color](#get_border_color)|Возвращает цвет границы, который связан с объектом образца.|
|[get_filter_mode](#get_filter_mode)|Возвращает `filter_mode` , связанную с объектом образца.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[оператор=](#operator_eq)|Перегружен. Оператор присвоения.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[address_mode](#address_mode)|Получает режим адресации объекта `sampler` объекта.|
|[border_color](#border_color)|Возвращает цвет границы `sampler` объекта.|
|[filter_mode](#filter_mode)|Получает режим фильтрации объекта `sampler` объекта.|

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

*_Filter_mode*<br/>
Режим фильтра, используемые в образце.

*_Address_mode*<br/>
Режим адресации, используемые в образце для всех измерений.

*_Border_color*<br/>
Цвет границы, если режим адреса — address_border. Значение по умолчанию — `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.

*_Другое*<br/>
[5] конструктор копии `sampler` объект для копирования в новый `sampler` экземпляра.

[6] конструктор перемещения `sampler` объект для перемещения в новый `sampler` экземпляра.

##  <a name="address_mode"></a> address_mode

Получает режим адресации объекта `sampler` объекта.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

##  <a name="border_color"></a> border_color

Возвращает цвет границы `sampler` объекта.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

##  <a name="filter_mode"></a> filter_mode

Получает режим фильтрации объекта `sampler` объекта.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

##  <a name="get_address_mode"></a> get_address_mode

Возвращает режим фильтра, настроенный для данного `sampler`.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Возвращаемое значение

Режим адреса, настроенный для образца.

##  <a name="get_border_color"></a> get_border_color

Возвращает цвет границы, настроенный для данного `sampler`.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Объект float_4, который содержит цвет границы.

##  <a name="get_filter_mode"></a> get_filter_mode

Возвращает режим фильтра, настроенный для данного `sampler`.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Возвращаемое значение

Режим фильтра, настроенный для образца.

##  <a name="operator_eq"></a> оператор =

Присваивает значение другого объекта дискретизатора существующему дискретизатору.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
[1] оператор присваивания копированием `sampler` копируемый в данный объект `sampler`.

[2] оператор присваивания перемещения `sampler` объект для перемещения в данную коллекцию `sampler`.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот экземпляр дискретизатора.

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
