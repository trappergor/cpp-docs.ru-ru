---
title: 'Функции пространство имен Concurrency::Graphics:: Direct3D | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d::get_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_sampler
- amp_graphics/Concurrency::graphics::direct3d::make_texture
dev_langs:
- C++
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ed95ed8df8a42dc62684c71a3005c2f33fecd18
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686338"
---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Функции пространство имен Concurrency::Graphics:: Direct3D
||||  
|-|-|-|  
|[get_sampler](#get_sampler)|[get_texture](#get_texture)|[make_sampler](#make_sampler)|  
|[make_texture](#make_texture)|[msad4](#msad4)|  

 
##  <a name="get_sampler"></a>  get_sampler  
 Get интерфейс конечного D3D пробы для данного сочетания клавиш просмотра, представляющий указанный образец объекта.  
  
```  
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,  
    const sampler& _Sampler) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Представление D3D сочетаний клавиш, на которой будет создаваться состояние D3D пробы.  
  
 `_Sampler`  
 Образец объект, для которого создается базового интерфейса состояние D3D пробы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель интерфейса IUnknown, соответствующее состоянию пробы D3D, представляющий данного образца.  
  
##  <a name="get_texture"></a>  get_texture  
 Возвращает указанный базовый интерфейс текстуры Direct3D [текстуры](texture-class.md) объекта.  
  
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
 `value_type`  
 Тип элемента текстуры.  
  
 `_Rank`  
 Ранг текстуры.  
  
 `_Texture`  
 Текстуры или представления текстуры, связанного с accelerator_view, для которого возвращается базового интерфейса текстуры Direct3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель интерфейса IUnknown, соответствующий базовый текстуры текстуры Direct3D.  
  
##  <a name="make_sampler"></a>  make_sampler  
 Создайте дискретизатор от указателя интерфейса состояние D3D пробы.  
  
```  
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_D3D_sampler`  
 Указатель интерфейса IUnknown состояние D3D пробы для создания образца из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дискретизатор представляет предоставленное состояние D3D пробы.  
  
##  <a name="make_texture"></a>  make_texture  
 Создает [текстуры](texture-class.md) объекта, используя указанные параметры.  
  
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
 `value_type`  
 Тип элементов в текстуре.  
  
 `_Rank`  
 Ранг текстуры.  
  
 `_Av`  
 Представление D3D сочетаний клавиш, на которой будет создаваться текстуры.  
  
 `_D3D_texture`  
 Указатель интерфейса IUnknown текстуры D3D создать текстуру с.  
  
 `_View_format`  
 DXGI формат, используемый для представления, созданные из этого текстуры. Передайте DXGI_FORMAT_UNKNOWN (по умолчанию), необходимо унаследовать формат базовый формат _D3D_texture и value_type этого шаблона. Указанный формат должен быть совместим с базовым форматом _D3D_texture.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текстуры с помощью предоставленного текстуры D3D.  
  
##  <a name="msad4"></a>  msad4  
 Сравнивает значение 4-байтовые ссылки и 8-байтное исходного значения и собирает вектор 4 сумм. Каждая сумма соответствует маскированные сумма абсолютный различия из разных байтов выравнивания значение ссылки и исходное значение.  
  
```  
inline uint4 msad4(
    uint _Reference,  
    uint2 _Source,  
    uint4 _Accum) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Reference`  
 Справочник по массив 4 байта в одно значение uint  
  
 `_Source`  
 Исходный массив 8 байт в векторе из двух значений uint.  
  
 `_Accum`  
 Вектор из 4 значений для добавления скрытого сумма абсолютный различия из разных байтов выравнивания значение ссылки и исходное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает вектор 4 сумм. Каждая сумма соответствует маскированные сумма абсолютный различия из разных байтов выравнивания значение ссылки и исходное значение.  

## <a name="requirements"></a>Требования  
 **Заголовок:** amp_graphics.h  
  
 **Пространство имен:** Concurrency::Graphics:: Direct3D 

## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::graphics::direct3d](concurrency-graphics-direct3d-namespace.md)
