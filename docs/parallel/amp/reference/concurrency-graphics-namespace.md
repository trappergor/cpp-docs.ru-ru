---
title: Пространство имен Concurrency::graphics
ms.date: 11/04/2016
f1_keywords:
- AMP_GRAPHICS/Concurrency
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
ms.openlocfilehash: ef61c93e062b375377a0afe62aa7f622f6c0d4ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375604"
---
# <a name="concurrencygraphics-namespace"></a>Пространство имен Concurrency::graphics

Пространство имен graphics предоставляет типы и функции, которые предназначены для программирования графики.

## <a name="syntax"></a>Синтаксис

```
namespace graphics;
```

## <a name="members"></a>Участники

### <a name="namespaces"></a>Пространства имен

|name|Описание|
|----------|-----------------|
|[Пространство имен Concurrency::graphics::direct3d](concurrency-graphics-direct3d-namespace.md)|Предоставляет функции для взаимодействия Direct3D.|

### <a name="typedefs"></a>Определения типов

|name|Описание|
|----------|-----------------|
|`uint`|Тип элемента для [класс uint_2](uint-2-class.md), [класс uint_3](uint-3-class.md), и [класс uint_4](uint-4-class.md). Определяется как `typedef unsigned int uint;`.|

### <a name="enumerations"></a>Перечисления

|name|Описание|
|----------|-----------------|
|[Перечисление address_mode](concurrency-graphics-namespace-enums.md#address_mode).|Задает режимы адреса, поддерживаемые для дискретизации текстур.|
|[Перечисление filter_mode](concurrency-graphics-namespace-enums.md#filter_mode)|Задает режимы фильтра, поддерживаемые для дискретизации текстур.|

### <a name="classes"></a>Классы

|name|Описание|
|----------|-----------------|
|[Класс texture](texture-class.md)|Текстура — это агрегат данных в accelerator_view в домене области памяти. Это коллекция переменных, по одной для каждого элемента в домене области памяти. Каждая переменная содержит значение, соответствующее типу-примитиву C++ (unsigned int, int, с плавающей запятой) или скалярному типу norm или unorm (определенному в concurrency::graphics) или подходящие типы короткого вектора, определенные в concurrency::graphics.|
|[Класс writeonly_texture_view](writeonly-texture-view-class.md)|Класс writeonly_texture_view предоставляет доступ к текстуре.|
|[Класс double_2](double-2-class.md)|Представляет короткий вектор из 2 `double` значения.|
|[Класс double_3](double-3-class.md)|Представляет короткий вектор из 3 `double` значения.|
|[Класс double_4](double-4-class.md)|Представляет короткий вектор из 4 `double` значения.|
|[Класс float_2](float-2-class.md)|Представляет короткий вектор из 2 `float` значения.|
|[Класс float_3](float-3-class.md)|Представляет короткий вектор из 3 `float` значения.|
|[Класс float_4](float-4-class.md)|Представляет короткий вектор из 4 `float` значения.|
|[Класс int_2](int-2-class.md)|Представляет короткий вектор из 2 `int` значения.|
|[Класс int_3](int-3-class.md)|Представляет короткий вектор из 3 `int` значения.|
|[Класс int_4](int-4-class.md)|Представляет короткий вектор из 4 `int` значения.|
|[Класс norm_2](norm-2-class.md)|Представляет короткий вектор из 2 `norm` значения.|
|[Класс norm_3](norm-3-class.md)|Представляет короткий вектор из 3 `norm` значения.|
|[Класс norm_4](norm-4-class.md)|Представляет короткий вектор из 4 `norm` значения.|
|[Класс uint_2](uint-2-class.md)|Представляет короткий вектор из 2 `uint` значения.|
|[Класс uint_3](uint-3-class.md)|Представляет короткий вектор из 3 `uint` значения.|
|[Класс uint_4](uint-4-class.md)|Представляет короткий вектор из 4 `uint` значения.|
|[Класс unorm_2](unorm-2-class.md)|Представляет короткий вектор из 2 `unorm` значения.|
|[Класс unorm_3](unorm-3-class.md)|Представляет короткий вектор из 3 `unorm` значения.|
|[Класс unorm_4](unorm-4-class.md)|Представляет короткий вектор из 4 `unorm` значения.|
|[Класс sampler](sampler-class.md)|Представляет конфигурацию образца, используемую для дискретизации текстур.|
|[Структура short_vector](short-vector-structure.md)|Предоставляет базовую реализацию короткого вектора значений.|
|[Структура short_vector_traits](short-vector-traits-structure.md)|Предоставляет получение длины и типа короткого вектора.|
|[Класс texture_view](texture-view-class.md)|Предоставляет доступ на чтение и запись к текстуре.|

### <a name="functions"></a>Функции

|name|Описание|
|----------|-----------------|
|[copy](concurrency-graphics-namespace-functions.md#copy)|Перегружен. Копирует содержимое исходной текстуры в буфер узла назначения.|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Перегружен. Асинхронно копирует содержимое исходной текстуры в буфер узла назначения.|

## <a name="requirements"></a>Требования

**Заголовок:** amp_graphics.h

**Пространство имен:** параллелизм

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
