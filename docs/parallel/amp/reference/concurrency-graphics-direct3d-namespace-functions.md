---
title: 'Функции пространства имен Concurrency::Graphics:: Direct3D'
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
ms.openlocfilehash: 71ce23d1238d852d42687be725de8153e938d6cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464731"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Функции пространства имен Concurrency::Graphics:: Direct3D

||||
|-|-|-|
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|
|[make_texture](#make_texture)|[msad4](#msad4)|

##  <a name="get_sampler"></a>  get_sampler

Получите интерфейс состояния дискретизатора D3D на ускорителе данного представления, представляющее указанный объект дискретизатора.

```
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,
    const sampler& _Sampler) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Av*<br/>
Представление ускорителя D3D, на котором будет создано состояние дискретизатора D3D.

*_Sampler*<br/>
Объект дискретизатора, для которого создается основной интерфейс состояния дискретизатора D3D.

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUnknown, соответствующий состоянию дискретизатора D3D, который представляет данный дискретизатор.

##  <a name="get_texture"></a>  get_texture

Получает интерфейс текстуры Direct3D, основе заданного [текстуры](texture-class.md) объекта.

```
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

*value_type*<br/>
Тип элементов текстуры.

*_Rank*<br/>
Ранг текстуры.

*_Texture*<br/>
Текстура или texture_view, связанные с accelerator_view, для которого возвращается базовый интерфейс Direct3D текстуры.

### <a name="return-value"></a>Возвращаемое значение

Указатель на интерфейс IUnknown, соответствующий Direct3D-текстуре, лежащей в основе текстуры.

##  <a name="make_sampler"></a>  make_sampler

Создайте дискретизатор из указателя интерфейса состояния дискретизатора D3D.

```
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_D3D_sampler*<br/>
Указатель на интерфейс IUnknown состояния дискретизатора D3D для создания дискретизатора.

### <a name="return-value"></a>Возвращаемое значение

Дискретизатор представляет предоставленное состояние дискретизатора D3D.

##  <a name="make_texture"></a>  make_texture

Создает [текстуры](texture-class.md) с использованием указанных параметров.

```
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

*value_type*<br/>
Тип элементов в текстуре.

*_Rank*<br/>
Ранг текстуры.

*_Av*<br/>
Представление ускорителя D3D, на которой будет создаваться текстуры.

*_D3D_texture*<br/>
Указатель на интерфейс IUnknown текстуры D3D для создания текстуры.

*_View_format*<br/>
Формат DXGI, используемый для представлений, созданных из этой текстуры. Передайте DXGI_FORMAT_UNKNOWN (по умолчанию) для получения формат от основного формата _d3d_texture и value_type этого шаблона. Предоставленный формат должен быть совместим с базовым форматом _d3d_texture.

### <a name="return-value"></a>Возвращаемое значение

Текстуры, используя предоставленную текстуру D3D.

##  <a name="msad4"></a>  msad4

Сравнивает 4-байтное ссылочное значение и 8-байтное исходное значение и накапливает вектор 4 сумм. Каждая сумма соответствует замаскированной сумме абсолютных различий различных выравниваний байтов между контрольным значением и исходным значением.

```
inline uint4 msad4(
    uint _Reference,
    uint2 _Source,
    uint4 _Accum) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Эталонных*<br/>
Массив ссылок из 4 байта в одном значении uint

*_Source*<br/>
Исходный массив из 8 байтов в векторе из двух значений uint.

*_Accum*<br/>
Вектор из 4 значений, добавляемых к замаскированной сумме абсолютных различий различных выравниваний байтов между контрольным значением и исходным значением.

### <a name="return-value"></a>Возвращаемое значение

Возвращает вектор 4 сумм. Каждая сумма соответствует замаскированной сумме абсолютных различий различных выравниваний байтов между контрольным значением и исходным значением.

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** Concurrency::Graphics:: Direct3D

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics::direct3d](concurrency-graphics-direct3d-namespace.md)
