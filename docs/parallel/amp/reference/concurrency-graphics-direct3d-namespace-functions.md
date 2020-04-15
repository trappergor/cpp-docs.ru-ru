---
title: Функции пространства имен Concurrency::graphics::direct3d
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 330c1aa94b1d122901fc23576686032400249d31
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376392"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Функции пространства имен Concurrency::graphics::direct3d

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

## <a name="get_sampler"></a><a name="get_sampler"></a>get_sampler

Получите интерфейс состояния d3D-сэмплера на данном представлении ускорителя, представляющем указанный объект сэмплера.

```cpp
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Представление ускорителя D3D, на котором должно быть создано состояние пробоотборникD D3D.

*_Sampler*<br/>
Объект сэмплер, для которого создается базовый интерфейс d3D-сэмплера.

### <a name="return-value"></a>Возвращаемое значение

Указатель интерфейса IUnknown, соответствующий состоянию d3D-сэмплера, представляющему данный сэмплер.

## <a name="get_texture"></a><a name="get_texture"></a>get_texture

Получает интерфейс текстуры Direct3D, лежащий в основе указанного объекта [текстуры.](texture-class.md)

```cpp
template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const writeonly_texture_view<value_type, _Rank>& _Texture) restrict(cpu);

template<
    typename value_type,
    int _Rank
>
_Ret_ IUnknown *get_texture(
    const texture_view<value_type, _Rank>& _Texture) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*Value_type*<br/>
Тип элемента текстуры.

*_Rank*<br/>
Ранг текстуры.

*_Texture*<br/>
Представление текстуры или текстуры, связанное с accelerator_view для которого возвращается базовый интерфейс текстуры Direct3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель интерфейса IUnknown, соответствующий текстуре Direct3D, лежащей в основе текстуры.

## <a name="make_sampler"></a><a name="make_sampler"></a>make_sampler

Создайте пробоотборник из указателя интерфейса состояния d3D-сэмплера.

```cpp
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_D3D_sampler*<br/>
IUnknown интерфейс указатель d3D сэмплер состояние для создания сэмплера из.

### <a name="return-value"></a>Возвращаемое значение

Сэмплер представляет предоставленное состояние пробоотбориров D3D.

## <a name="make_texture"></a><a name="make_texture"></a>make_texture

Создает [объект текстуры](texture-class.md) с помощью указанных параметров.

```cpp
template<
    typename value_type,
    int _Rank
>
texture<value_type, _Rank> make_texture(
    const Concurrency::accelerator_view& _Av,
    _In_ IUnknown* _D3D_texture,
    DXGI_FORMAT _View_format = DXGI_FORMAT_UNKNOWN) restrict(cpu);
```

### <a name="parameters"></a>Параметры

*Value_type*<br/>
Тип элементов в текстуре.

*_Rank*<br/>
Ранг текстуры.

*_Av*<br/>
Вид ускорителя D3D, на котором должна быть создана текстура.

*_D3D_texture*<br/>
IUnknown интерфейс указатель текстуры D3D для создания текстуры из.

*_View_format*<br/>
Формат DXGI для использования для представлений, созданных из этой текстуры. Передайте DXGI_FORMAT_UNKNOWN (по умолчанию) для получения формата из базового формата _D3D_texture и value_type этого шаблона. Предоставленный формат должен быть совместим с базовым форматом _D3D_texture.

### <a name="return-value"></a>Возвращаемое значение

Текстура с использованием предоставленной текстуры D3D.

## <a name="msad4"></a><a name="msad4"></a>msad4

Сравнивает эталонное значение 4 байта и исходное значение 8 байт и аккумулирует вектор в 4 сум. Каждая сумма соответствует замаскированной сумме абсолютных различий различных выравниваний байта между эталонным значением и исходным значением.

```cpp
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Reference*<br/>
Справочный массив из 4 байтов в одном значении uint

*_Source*<br/>
Исходный массив из 8 байтов в векторе двух значений uint.

*_Accum*<br/>
Вектор 4 значений, которые должны быть добавлены к замаскированной сумме абсолютных различий различных выравниваний байта между эталонным значением и исходным значением.

### <a name="return-value"></a>Возвращаемое значение

Возвращает вектор 4 суммы. Каждая сумма соответствует замаскированной сумме абсолютных различий различных выравниваний байта между эталонным значением и исходным значением.

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** Параллель::: :direct3d

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency::graphics::direct3d](concurrency-graphics-direct3d-namespace.md)
