---
title: "Функции пространство имен Concurrency::Graphics:: Direct3D | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11ee1d42-333e-4ae9-95ac-4cf68c06d13d
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: aa7e91237eaa9ced297e2c5748359c23bb436df8
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencygraphicsdirect3d-namespace-functions"></a>Функции пространство имен Concurrency::Graphics:: Direct3D
||||  
|-|-|-|  
|[Функция get_sampler](#get_sampler)|[Функция get_texture](#get_texture)|[Функция make_sampler](#make_sampler)|  
|[Функция make_texture](#make_texture)|[Функция msad4](#msad4)|  
  
##  <a name="a-namegetsamplera--getsampler-function"></a><a name="get_sampler"></a>Функция get_sampler  
 Get интерфейс D3D пробы состояние данного сочетания клавиш просмотра, представляющий указанный образец объекта.  
  
```  
IUnknown* get_sampler(
    const Concurrency::accelerator_view& _Av,  
    const sampler& _Sampler) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Av`  
 Представление D3D сочетаний клавиш, на которой будет создаваться состояние пробы D3D.  
  
 `_Sampler`  
 Образец объекта, для которого создается базовый интерфейс состояния D3D пробы.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель интерфейса IUnknown, соответствующее состоянию D3D пробы, представляющий данного образца.  
  
##  <a name="a-namegettexturea--gettexture-function"></a><a name="get_texture"></a>Функция get_texture  
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
 Текстуры или представления текстуры, связанного с accelerator_view, для которого возвращается базовый интерфейс текстуры Direct3D.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель интерфейса IUnknown, соответствующий базовый текстуры Direct3D-текстуру.  
  
##  <a name="a-namemakesamplera--makesampler-function"></a><a name="make_sampler"></a>Функция make_sampler  
 Создайте образец из указателя на интерфейс состояния D3D пробы.  
  
```  
sampler make_sampler(_In_ IUnknown* _D3D_sampler) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_D3D_sampler`  
 Указатель на интерфейс IUnknown состояния пробы D3D для создания образца из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Образец представляет состояние пробы предоставленный D3D.  
  
##  <a name="a-namemaketexturea--maketexture-function"></a><a name="make_texture"></a>Функция make_texture  
 Создает [текстуры](texture-class.md) объекта, используя заданные параметры.  
  
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
 Указатель на интерфейс IUnknown текстуры D3D создать текстуру с.  
  
 `_View_format`  
 DXGI формат, используемый для представления, созданные из этой текстуры. Передайте DXGI_FORMAT_UNKNOWN (по умолчанию), чтобы унаследовать формат базовый формат _D3D_texture и value_type этого шаблона. Указанный формат должен быть совместим с базовым форматом _D3D_texture.  
  
### <a name="return-value"></a>Возвращаемое значение  
 С помощью предоставленного текстуры D3D текстуры.  
  
##  <a name="a-namemsad4a--msad4-function"></a><a name="msad4"></a>Функция msad4  
 Сравнивает значение 4-байтовое ссылки и 8-байтовое исходного значения и собирает вектора 4 сумм. Каждая сумма соответствует маской сумму абсолютные различия из различных байтовых выравнивания значение ссылки и исходное значение.  
  
```  
inline uint4 msad4(
    uint _Reference,  
    uint2 _Source,  
    uint4 _Accum) restrict(amp);
```  
  
### <a name="parameters"></a>Параметры  
 `_Reference`  
 Массив ссылок 4 байта в одно значение uint  
  
 `_Source`  
 Исходный массив в векторе из двух значений uint 8 байт.  
  
 `_Accum`  
 Вектор значений 4 для добавления скрытого сумму абсолютные различия из различных байтовых выравнивания значение ссылки и исходное значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает вектор 4 сумм. Каждая сумма соответствует маской сумму абсолютные различия из различных байтовых выравнивания значение ссылки и исходное значение.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency::Graphics:: Direct3D](concurrency-graphics-direct3d-namespace.md)

