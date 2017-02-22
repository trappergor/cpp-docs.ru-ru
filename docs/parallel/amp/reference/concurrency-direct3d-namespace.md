---
title: "Пространство имен Concurrency::direct3d | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::direct3d"
  - "amprt/Concurrency::direct3d"
  - "amp_short_vectors/Concurrency::direct3d"
  - "amp_graphics/Concurrency::direct3d"
  - "amp_math/Concurrency::direct3d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "direct3d - пространство имен"
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# Пространство имен Concurrency::direct3d
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Пространство имен `direct3d` предоставляет функции, которые поддерживают взаимодействие с D3D.  Оно позволяет прозрачным образом использовать D3D \-ресурсы для вычислений в AMP\-коде, а также использовать ресурсы, созданные в AMP\-коде, в D3D\-коде без создания промежуточных резервных копий.  Существует возможность инкрементально ускорять вычислительно затратные части DirectX приложений с помощью C\+\+ AMP, и использовать D3D API на данных, полученных из AMP вычислений.  
  
## Синтаксис  
  
```  
namespace direct3d;  
```  
  
## Члены  
  
### Классы  
  
|Name|Описание|  
|----------|--------------|  
|[Класс scoped\_d3d\_access\_lock](../Topic/scoped_d3d_access_lock%20Class.md)|Оболочка RAII для блокирования доступа D3D объекта `accelerator_view`.|  
  
### Структуры  
  
|Name|Описание|  
|----------|--------------|  
|[Структура adopt\_d3d\_access\_lock\_t](../../../parallel/amp/reference/adopt-d3d-access-lock-t-structure.md)|Тип тега, чтобы указать, что блокировка доступа D3D должна быть принята, а не приобретена.|  
  
### Функции  
  
|Name|Описание|  
|----------|--------------|  
|[Функция abs](../Topic/abs%20Function.md)|Возвращает абсолютное значение аргумента|  
|[Функция clamp](../Topic/clamp%20Function.md)|Перегружен.  Привязывает \_X к указанному диапазону между \_Min и \_Max|  
|[Функция countbits](../Topic/countbits%20Function.md)|Подсчитывает число установленных битов в \_X|  
|[Функция create\_accelerator\_view](../Topic/create_accelerator_view%20Function.md)|Создает объект [Класс accelerator\_view](../Topic/accelerator_view%20Class.md) из указателя на интерфейс устройства Direct3D|  
|[Функция d3d\_access\_lock](../Topic/d3d_access_lock%20Function.md)|Получает блокировку на accelerator\_view для безопасного выполнения операций D3D на ресурсах общих с accelerator\_view.|  
|[Функция d3d\_access\_try\_lock](../Topic/d3d_access_try_lock%20Function.md)|Попытка получить блокировку доступа D3D на accelerator\_view без блокировки.|  
|[Функция d3d\_access\_unlock](../Topic/d3d_access_unlock%20Function.md)|Освобождение блокировки доступа D3D для заданного accelerator\_view.|  
|[Функция firstbithigh](../Topic/firstbithigh%20Function.md)|Получает расположение первого установленного бита в \_X, начиная с наиболее старших битов и продолжая в сторону младших|  
|[Функция firstbitlow](../Topic/firstbitlow%20Function.md)|Получает расположение первого установленного бита в \_X, начиная с наиболее младших битов и продолжая в сторону старших|  
|[Функция get\_buffer](../Topic/get_buffer%20Function.md)|Получите интерфейс буфера D3D, лежащий в основе массива.|  
|[Функция imax](../Topic/imax%20Function.md)|Сравнивает два значения, возвращая то значение, которое больше.|  
|[Функция imin](../Topic/imin%20Function.md)|Сравнивает два значения, возвращая то значение, которое меньше.|  
|[Функция is\_timeout\_disabled](../Topic/is_timeout_disabled%20Function.md)|Возвращает логический флаг, указывающий, отключено ли время ожидания для заданного accelerator\_view.|  
|[Функция mad](../Topic/mad%20Function.md)|Перегружен.  Выполняет арифметическую операцию умножения и сложения трех аргументов: \_X \* \_Y \+ \_Z|  
|[Функция make\_array](../Topic/make_array%20Function.md)|Создайте массив из указателя интерфейса буфера D3D.|  
|[Функция noise](../Topic/noise%20Function.md)|Создает случайное значение при помощи алгоритма шума Перлина|  
|[Функция radians](../Topic/radians%20Function.md)|Преобразовывает значение \_X из градусов в радианы|  
|[Функция rcp](../Topic/rcp%20Function.md)|Вычисляет быструю, приблизительную обратную величину аргумента|  
|[Функция reversebits](../Topic/reversebits%20Function.md)|Изменяет порядок бит в \_X на обратный|  
|[Функция saturate](../Topic/saturate%20Function.md)|Ограничивает \_X в диапазоне от 0 до 1|  
|[Функция sign](../Topic/sign%20Function.md)|Перегружен.  Возвращает знак аргумента|  
|[Функция smoothstep](../Topic/smoothstep%20Function.md)|Возвращает гладкую эрмитову интерполяцию между 0 и 1, если \_X в диапазоне \[\_Min, \_Max\].|  
|[Функция step](../Topic/step%20Function.md)|Сравнивает два значения, возвращая 0 или 1 в зависимости от того, какое значение больше|  
|[Функция umax](../Topic/umax%20Function.md)|Сравнивает два беззнаковых значения, возвращая то значение, которое больше.|  
|[Функция umin](../Topic/umin%20Function.md)|Сравнивает два беззнаковых значения, возвращая то значение, которое меньше.|  
  
## Требования  
 **Заголовок:** amp.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)