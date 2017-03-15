---
title: "&lt;поток&gt; | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 9b32de86d2ec84017157cccf1a05b9e9b6802e47
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt"></a>&lt;поток&gt;
Включать стандартный заголовок \<поток настроек для определения класса `thread` и различные вспомогательные функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В коде, который компилируется с помощью **/CLR**, этот заголовок будет заблокирован.  
  
 `__STDCPP_THREADS__` Макрос представляет собой ненулевое значение, указывающее, что потоки поддерживаются этот заголовок.  
  
## <a name="members"></a>Члены  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс thread](../standard-library/thread-class.md)|Определяет объект, который позволяет наблюдать и управлять потоком выполнения в приложении.|  
  
### <a name="public-structures"></a>Открытые структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура hash (стандартная библиотека C++)](../standard-library/hash-structure-stl.md)|Определяет, возвращает значение, которое однозначно определить с помощью функции-члена `thread::id`. Функция-член определяет [хэш](../standard-library/hash-class.md) функцию, которая подходит для сопоставления значений типа `thread::id` распределение значений индекса.|  
  
### <a name="public-functions"></a>Открытые функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[Функция get_id](../standard-library/thread-functions.md#get_id_function)|Уникально идентифицирует текущий поток выполнения.|  
|[Функция sleep_for](../standard-library/thread-functions.md#sleep_for_function)|Блокирует вызывающий поток.|  
|[Функция sleep_until](../standard-library/thread-functions.md#sleep_until_function)|Блокирует вызывающий поток по крайней мере до указанного времени.|  
|[Функция swap](../standard-library/thread-functions.md#swap_function)|Меняет местами два состояния `thread` объектов.|  
|[Функция yield](../standard-library/thread-functions.md#yield_function)|Сигнализирует операционной системе, что необходимо запустить другие потоки, даже если в обычной ситуации текущий поток продолжал бы выполняться.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор настроек =-Оператор](../standard-library/thread-operators.md#operator_gt__eq)|Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.|  
|[оператор настроек Оператор](../standard-library/thread-operators.md#operator_gt_)|Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.|  
|[оператор<=></=>](../standard-library/thread-operators.md#operator_lt__eq)|Определяет, справедливо ли, что один из объектов `thread::id` меньше другого или равен ему.|  
|[оператор<>](../standard-library/thread-operators.md#operator_lt_)|Определяет, справедливо ли, что один объект `thread::id` меньше другого.|  
|[оператор! =-оператор](../standard-library/thread-operators.md#operator_neq)|Проверяет неравенство двух объектов `thread::id`.|  
|[оператор ==-оператор](../standard-library/thread-operators.md#operator_eq_eq)|Сравнивает два объекта `thread::id` на равенство.|  
|[оператор<>](../standard-library/thread-operators.md#operator_lt__lt_)|Вставляет текстовое представление объекта `thread::id` в поток.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


