---
title: "Пространство имен Concurrency::Direct3D | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 94e0542910484166a01bd79beb9dfaa805aae6cd
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
|[abs](concurrency-direct3d-namespace-functions-amp.md#abs)|Возвращает абсолютное значение аргумента|  
|[Скоба](concurrency-direct3d-namespace-functions-amp.md#clamp)|Перегружен. Фиксирует _X в заданный диапазон _Min и _Max|  
|[countbits](concurrency-direct3d-namespace-functions-amp.md#countbits)|Подсчитывает количество набор битов в _X|  
|[create_accelerator_view](concurrency-direct3d-namespace-functions-amp.md#create_accelerator_view)|Создает [класс accelerator_view](accelerator-view-class.md) указателя на интерфейс устройства Direct3D|  
|[d3d_access_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_lock)|Получает блокировку для безопасного выполнения операций D3D ресурсов, совместно с accelerator_view accelerator_view|  
|[d3d_access_try_lock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_try_lock)|Попытка получить блокировку доступа D3D accelerator_view без блокировки.|  
|[d3d_access_unlock](concurrency-direct3d-namespace-functions-amp.md#d3d_access_unlock)|Снять блокировку доступа D3D данного accelerator_view.|  
|[firstbithigh](concurrency-direct3d-namespace-functions-amp.md#firstbithigh)|Возвращает положение первого значащего разряда в _X, начиная от наибольший бит и далее вниз|  
|[firstbitlow](concurrency-direct3d-namespace-functions-amp.md#firstbitlow)|Возвращает положение первого значащего разряда в _X, начиная от младший бит и далее вверх|  
|[get_buffer](concurrency-direct3d-namespace-functions-amp.md#get_buffer)|Получите интерфейс буфера D3D базовый массив.|  
|[iMax](concurrency-direct3d-namespace-functions-amp.md#imax)|Сравнивает два значения и возвращает значение, которое больше.|  
|[imin](concurrency-direct3d-namespace-functions-amp.md#imin)|Сравнивает два значения и возвращает значение, которое меньше.|  
|[is_timeout_disabled](concurrency-direct3d-namespace-functions-amp.md#is_timeout_disabled)|Возвращает указатель логического типа, указывающее, отключено ли время ожидания для указанного accelerator_view.|  
|[MAD](concurrency-direct3d-namespace-functions-amp.md#mad)|Перегружен. Выполняет операцию арифметического умножения и добавления на три аргумента: _X * _Y + _Z|  
|[make_array](concurrency-direct3d-namespace-functions-amp.md#make_array)|Создайте массив из указателя на интерфейс D3D буфера.|  
|[шум](concurrency-direct3d-namespace-functions-amp.md#noise)|Создает случайное значение с помощью алгоритма шума Перлина|  
|[радианы](concurrency-direct3d-namespace-functions-amp.md#radians)|Преобразует _X из градусов в радианы|  
|[rcp](concurrency-direct3d-namespace-functions-amp.md#rcp)|Вычисляет быстрый, приблизительное обратное аргумента|  
|[reversebits](concurrency-direct3d-namespace-functions-amp.md#reversebits)|Изменяет порядок битов _X|  
|[перегрузке](concurrency-direct3d-namespace-functions-amp.md#saturate)|Фиксирует _X в диапазоне от 0 до 1|  
|[вход](concurrency-direct3d-namespace-functions-amp.md#sign)|Перегружен. Возвращает знак аргумента|  
|[smoothstep](concurrency-direct3d-namespace-functions-amp.md#smoothstep)|Возвращает smooth Hermite интерполяцию между 0 и 1, если _X находится в диапазоне [_Min, _Max].|  
|[Шаг](concurrency-direct3d-namespace-functions-amp.md#step)|Сравнивает два значения и возвращает 0 или 1, в зависимости от того, какое значение больше.|  
|[UMAX](concurrency-direct3d-namespace-functions-amp.md#umax)|Сравнивает два значения без знака, возвращая значение, которое больше.|  
|[umin](concurrency-direct3d-namespace-functions-amp.md#umin)|Сравнивает два значения без знака, возвращая значение, которое меньше.|  

## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

