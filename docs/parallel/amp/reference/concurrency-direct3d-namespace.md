---
title: "Пространство имен Concurrency::Direct3D | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
dev_langs: C++
helpviewer_keywords: direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46b4962e30a6990f6de2c67437fc2af3989c2407
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="concurrencydirect3d-namespace"></a>Пространство имен Concurrency::direct3d
`direct3d` Пространство имен предоставляет функции, поддерживающие взаимодействие D3D. Он обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP, а также разрешает использование ресурсов, созданные в AMP в коде D3D, не создавая промежуточные резервированием. Можно постепенно ускорения большим объемом вычислений разделы приложений DirectX с помощью C++ AMP и использовать этот API D3D в формируемые AMP вычисления данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Класс scoped_d3d_access_lock](scoped-d3d-access-lock-class.md)|Для блокировки доступа D3D программой-оболочкой RAII `accelerator_view` объекта.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Структура adopt_d3d_access_lock_t](adopt-d3d-access-lock-t-structure.md)|Тип тега для указания блокировки доступа D3D должны приняла, а не получена.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание:|  
|----------|-----------------|  
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Возвращает абсолютное значение аргумента|  
|[CLAMP](concurrency-direct3d-namespace-functions-amp.md#clamp)|Перегружен. Фиксирует _X в заданный диапазон _Min и _Max|  
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Подсчитывает количество набор бит в _X|  
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Создает [класс accelerator_view](accelerator-view-class.md) из указателя на интерфейс устройства Direct3D|  
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Получает блокировку accelerator_view, чтобы безопасно выполнять операции D3D ресурсы совместно с accelerator_view|  
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Попытка получить блокировку доступа D3D accelerator_view без блокировки.|  
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Снять блокировку доступа D3D данного accelerator_view.|  
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Получает расположение первый набор бит _X, начиная с наивысшим бит и работа вниз|  
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Получает расположение первый набор бит _X, начиная с младший бит и работа вверх|  
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Получение интерфейса буфера D3D базовый массив.|  
|[iMax](concurrency-direct3d-namespace-functions-amp.md#imax)|Сравнивает два значения и возвращает значение, которое больше.|  
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Сравнивает два значения и возвращает значение, которое меньше.|  
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Возвращает логический флаг, указывающее, запрещен ли accelerator_view указанного времени ожидания.|  
|[MAD](concurrency-direct3d-namespace-functions-amp.md#mad)|Перегружен. Выполняет операцию арифметического умножения или добавления на три аргумента: _X * _Y + _Z|  
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Создайте массив в указатель на интерфейс D3D буфера.|  
|[шума](concurrency-direct3d-namespace-functions-amp.md#noise)|Создает случайное значение с помощью алгоритма шума Перлина|  
|[RADIANS](concurrency-direct3d-namespace-functions-amp.md#radians)|Преобразование _X из градусов в радианы|  
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Вычисляет приблизительные, быстро обратное аргумента|  
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Изменяет порядок биты в _X|  
|[saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|Фиксирует _X в диапазоне от 0 до 1|  
|[вход](concurrency-direct3d-namespace-functions-amp.md#sign)|Перегружен. Возвращает знак значения аргумента|  
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Возвращает smooth интерполяции Hermite между 0 и 1, если _X находится в диапазоне [_Min, _Max].|  
|[Шаг](concurrency-direct3d-namespace-functions-amp.md#step)|Сравнивает два значения и возвращает 0 или 1, в зависимости от того, какое значение больше.|  
|[UMAX](concurrency-direct3d-namespace-functions-amp.md#umax)|Сравнивает два значения без знака, возвращая значение, которое больше.|  
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Сравнивает два значения без знака, возвращая значение, которое меньше.|  

## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
