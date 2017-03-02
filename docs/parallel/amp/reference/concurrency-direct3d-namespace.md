---
title: "Пространство имен Concurrency::Direct3D | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::direct3d
- amprt/Concurrency::direct3d
- amp_short_vectors/Concurrency::direct3d
- amp_graphics/Concurrency::direct3d
- amp_math/Concurrency::direct3d
dev_langs:
- C++
helpviewer_keywords:
- direct3d namespace
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fe9121d6e054446d3adb70da9f78884f4198517e
ms.lasthandoff: 02/24/2017

---
# <a name="concurrencydirect3d-namespace"></a>Пространство имен Concurrency::direct3d
`direct3d` Пространство имен предоставляет функции, поддерживающие взаимодействие D3D. Он обеспечивает эффективное использование ресурсов D3D для вычисления в код управления Устройством, а также разрешить использовать ресурсы, созданные в AMP в коде D3D без создания промежуточных резервированием. Можно постепенно ускорения большим объемом вычислений разделы приложений DirectX с помощью C++ AMP и использовать D3D API на данные, полученные из AMP вычислений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace direct3d;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс scoped_d3d_access_lock](scoped-d3d-access-lock-class.md)|Для блокировки доступа D3D программой-оболочкой RAII `accelerator_view` объекта.|  
  
### <a name="structures"></a>Структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура adopt_d3d_access_lock_t](adopt-d3d-access-lock-t-structure.md)|Тип тега для указания блокировки доступа D3D должны приняты, а не получена.|  
  
### <a name="functions"></a>Функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция ABS](concurrency-direct3d-namespace-functions-amp.md#abs)|Возвращает абсолютное значение аргумента|  
|[Функция CLAMP](concurrency-direct3d-namespace-functions-amp.md#clamp)|Перегружен. Фиксирует _X в заданный диапазон _Min и _Max|  
|[Функция countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Подсчитывает количество набор битов в _X|  
|[Функция create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Создает [класс accelerator_view](accelerator-view-class.md) указателя на интерфейс устройства Direct3D|  
|[Функция d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Получает блокировку для безопасного выполнения операций D3D ресурсов, совместно с accelerator_view accelerator_view|  
|[Функция d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Попытка получить блокировку доступа D3D accelerator_view без блокировки.|  
|[Функция d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Снять блокировку доступа D3D данного accelerator_view.|  
|[Функция firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Возвращает положение первого значащего разряда в _X, начиная от наибольший бит и далее вниз|  
|[Функция firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Возвращает положение первого значащего разряда в _X, начиная от младший бит и далее вверх|  
|[Функция get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Получите интерфейс буфера D3D базовый массив.|  
|[Функция iMax](concurrency-direct3d-namespace-functions-amp.md#imax)|Сравнивает два значения и возвращает значение, которое больше.|  
|[Функция imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Сравнивает два значения и возвращает значение, которое меньше.|  
|[Функция is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Возвращает указатель логического типа, указывающее, отключено ли время ожидания для указанного accelerator_view.|  
|[Функция MAD](concurrency-direct3d-namespace-functions-amp.md#mad)|Перегружен. Выполняет операцию арифметического умножения и добавления на три аргумента: _X * _Y + _Z|  
|[Функция make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Создайте массив из указателя на интерфейс D3D буфера.|  
|[Функция noise](concurrency-direct3d-namespace-functions-amp.md#noise)|Создает случайное значение с помощью алгоритма шума Перлина|  
|[Функция RADIANS](concurrency-direct3d-namespace-functions-amp.md#radians)|Преобразует _X из градусов в радианы|  
|[Функция rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Вычисляет быстрый, приблизительное обратное аргумента|  
|[Функция reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Изменяет порядок битов _X|  
|[Функция saturate](concurrency-direct3d-namespace-functions-amp.md#saturate)|Фиксирует _X в диапазоне от 0 до 1|  
|[Функция Sign](concurrency-direct3d-namespace-functions-amp.md#sign)|Перегружен. Возвращает знак аргумента|  
|[Функция smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Возвращает smooth Hermite интерполяцию между 0 и 1, если _X находится в диапазоне [_Min, _Max].|  
|[Функция Step](concurrency-direct3d-namespace-functions-amp.md#step)|Сравнивает два значения и возвращает 0 или 1, в зависимости от того, какое значение больше.|  
|[Функция UMAX](concurrency-direct3d-namespace-functions-amp.md#umax)|Сравнивает два значения без знака, возвращая значение, которое больше.|  
|[Функция umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Сравнивает два значения без знака, возвращая значение, которое меньше.|  

## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

