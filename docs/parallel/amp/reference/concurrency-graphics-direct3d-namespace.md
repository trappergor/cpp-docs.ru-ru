---
title: Пространство имен Concurrency::graphics::direct3d
ms.date: 11/04/2016
f1_keywords:
- amp_graphics/Concurrency::graphics::direct3d
- amp_short_vectors/Concurrency::graphics::direct3d
ms.assetid: be283331-07cf-46e4-91a1-e8aa85d4ec8e
ms.openlocfilehash: 8fb03edd63c612fd070e50e2f5d229cd8e207812
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57280801"
---
# <a name="concurrencygraphicsdirect3d-namespace"></a>Пространство имен Concurrency::graphics::direct3d

Предоставляет [get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture) и [make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture) методы.

## <a name="syntax"></a>Синтаксис

```
namespace direct3d;
```

## <a name="members"></a>Участники

### <a name="functions"></a>Функции

|Имя<br /><br /> Описание:|
|--------------------------|
|[get_sampler](concurrency-graphics-direct3d-namespace-functions.md#get_sampler)<br /><br /> Получите интерфейс состояния дискретизатора Direct3D на ускорителе данного представления, представляющее указанный объект дискретизатора.|
|[get_texture](concurrency-graphics-direct3d-namespace-functions.md#get_texture)<br /><br /> Получает интерфейс текстуры Direct3D, основе заданного [текстуры](texture-class.md) объекта.|
|[make_sampler](concurrency-graphics-direct3d-namespace-functions.md#make_sampler)<br /><br /> Создайте дискретизатор из указателя интерфейса состояния дискретизатора Direct3D.|
|[make_texture](concurrency-graphics-direct3d-namespace-functions.md#make_texture)<br /><br /> Создает [текстуры](texture-class.md) с использованием указанных параметров.|
|[msad4](concurrency-graphics-direct3d-namespace-functions.md#msad4)<br /><br /> Сравнивает 4-байтное ссылочное значение и 8-байтное исходное значение и накапливает вектор 4 сумм.|

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** Concurrency::Graphics

## <a name="see-also"></a>См. также

[Пространство имен Concurrency::graphics](concurrency-graphics-namespace.md)
