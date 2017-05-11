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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 496269689428e73dc78893092844afb1650da20d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltthreadgt"></a>&lt;thread&gt;
Включите стандартный заголовок \<поток > Определение класса `thread` и различные вспомогательные функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  В коде, скомпилированном с помощью **/CLR**, этот заголовок блокируется.  
  
 `__STDCPP_THREADS__` Макрос определен как ненулевое значение, чтобы указать, что этот заголовок поддерживает потоков.  
  
## <a name="members"></a>Члены  
  
### <a name="public-classes"></a>Открытые классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс thread](../standard-library/thread-class.md)|Определяет объект, который используется для просмотра и управления потоком выполнения в приложении.|  
  
### <a name="public-structures"></a>Открытые структуры  
  
|Имя|Описание|  
|----------|-----------------|  
|[Структура hash (стандартная библиотека C++)](../standard-library/hash-structure-stl.md)|Определяет функцию-член возвращает значение, которое однозначно определяется `thread::id`. Функция-член определяет [хэш](../standard-library/hash-class.md) функция, которая подходит для сопоставления значений типа `thread::id` распределение значений индекса.|  
  
### <a name="public-functions"></a>Открытые функции  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_id](../standard-library/thread-functions.md#get_id)|Уникально идентифицирует текущий поток выполнения.|  
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Блокирует вызывающий поток.|  
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Блокирует вызывающий поток по крайней мере до указанного времени.|  
|[swap](../standard-library/thread-functions.md#swap)|Меняет местами два состояния `thread` объектов.|  
|[yield](../standard-library/thread-functions.md#yield)|Сигнализирует операционной системе, что необходимо запустить другие потоки, даже если в обычной ситуации текущий поток продолжал бы выполняться.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор > =-оператор](../standard-library/thread-operators.md#op_gt_eq)|Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.|  
|[оператор > оператор](../standard-library/thread-operators.md#op_gt)|Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.|  
|[оператор < =-оператор](../standard-library/thread-operators.md#op_lt_eq)|Определяет, справедливо ли, что один из объектов `thread::id` меньше другого или равен ему.|  
|[оператор < оператор](../standard-library/thread-operators.md#op_lt)|Определяет, справедливо ли, что один объект `thread::id` меньше другого.|  
|[оператор! =-оператор](../standard-library/thread-operators.md#op_neq)|Проверяет неравенство двух объектов `thread::id`.|  
|[оператор ==-оператор](../standard-library/thread-operators.md#op_eq_eq)|Сравнивает два объекта `thread::id` на равенство.|  
|[оператор << оператор](../standard-library/thread-operators.md#op_lt_lt)|Вставляет текстовое представление объекта `thread::id` в поток.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


