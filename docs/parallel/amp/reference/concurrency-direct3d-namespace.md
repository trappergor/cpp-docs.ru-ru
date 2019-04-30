---
title: Пространство имен Concurrency::direct3d
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
ms.openlocfilehash: 6afbd7b3a3f4280ad658c1cb9d8802cc3251d0ed
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405486"
---
# <a name="concurrencydirect3d-namespace"></a>Пространство имен Concurrency::direct3d

`direct3d` Пространство имен предоставляет функции, поддерживающие взаимодействие с D3D. Оно позволяет прозрачным образом использовать D3D-ресурсы для вычислений в AMP-коде, а также использовать ресурсы, созданные в AMP в коде D3D без создания промежуточных резервных копий. Кроме того, можно постепенно ускорять вычислительно части DirectX приложений с помощью C++ AMP и использовать D3D API на данных, полученных из AMP вычислений.

## <a name="syntax"></a>Синтаксис

```
namespace direct3d;
```

## <a name="members"></a>Участники

### <a name="classes"></a>Классы

|name|Описание|
|----------|-----------------|
|[Класс scoped_d3d_access_lock](scoped-d3d-access-lock-class.md)|Оболочка RAII для блокирования доступа D3D `accelerator_view` объекта.|

### <a name="structures"></a>Структуры

|name|Описание|
|----------|-----------------|
|[Структура adopt_d3d_access_lock_t](adopt-d3d-access-lock-t-structure.md)|Тип тега, чтобы указать блокировку доступа D3D должны соблюдать, а не получена.|

### <a name="functions"></a>Функции

|name|Описание|
|----------|-----------------|
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Возвращает абсолютное значение аргумента|
|[clamp](concurrency-direct3d-namespace-functions-amp.md#clamp)|Перегружен. Ограничивает _X в заданный диапазон диапазону между _Min и _Max|
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Подсчитывает число установленных битов в _X|
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Создает [класс accelerator_view](accelerator-view-class.md) из указателя на интерфейс устройства Direct3D|
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Получает блокировку на accelerator_view для безопасного выполнения операций D3D на ресурсах общих с accelerator_view|
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Попытки получить блокировку доступа D3D на accelerator_view без блокировки.|
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Снять блокировку доступа D3D для заданного accelerator_view.|
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Получает расположение первого установленного бита в _X, начиная с наиболее старших битов и продолжая вниз|
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Получает расположение первого установленного бита в _X, начиная с младший бит и продолжая вверх|
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Получите интерфейс буфера D3D, базовый массив.|
|[imax](concurrency-direct3d-namespace-functions-amp.md#imax)|Сравнивает два значения, возвращая значение, которое больше.|
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Сравнивает два значения, возвращая значение, которое меньше.|
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Возвращает логический флаг, указывающее, отключено ли время ожидания для заданного accelerator_view.|
|[MAD](concurrency-direct3d-namespace-functions-amp.md#mad)|Перегружен. Выполняет арифметическую операцию сложения трех аргументов: _X \* _Y + _Z|
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Создайте массив из указателя интерфейса буфера D3D.|
|[шума](concurrency-direct3d-namespace-functions-amp.md#noise)|Создает случайное значение с помощью алгоритма шума Перлина|
|[radians](concurrency-direct3d-namespace-functions-amp.md#radians)|Преобразовывает значение _X из градусов в радианы.|
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Вычисляет быструю, приблизительную обратную величину аргумента|
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Изменяет порядок бит в _X на обратный|
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|Ограничивает _X в диапазоне от 0 до 1|
|[sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Перегружен. Возвращает знак аргумента|
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Возвращает гладкую Эрмитову интерполяцию между 0 и 1, если _X в диапазоне [_Min, _Max].|
|[Шаг](concurrency-direct3d-namespace-functions-amp.md#step)|Сравнивает два значения, возвращая 0 или 1, в зависимости от того, какое значение больше|
|[umax](concurrency-direct3d-namespace-functions-amp.md#umax)|Сравнивает два беззнаковых значения, возвращая значение, которое больше.|
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Сравнивает два беззнаковых значения, возвращая значение, которое меньше.|

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен:** параллелизм

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
