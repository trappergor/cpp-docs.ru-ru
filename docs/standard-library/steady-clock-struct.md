---
title: "Структура steady_clock | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 332008ed313eeae7f04f39165424a9280c2aed8c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="steadyclock-struct"></a>Структура steady_clock
Представляет часы `steady`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct steady_clock;  
```  
  
## <a name="remarks"></a>Примечания  
 В Windows объект steady_clock создает оболочку для функции QueryPerformanceCounter.  
  
 Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда не больше значений, возвращаемых при последующих вызовах `now()`.  
  
 Часы считаются *постоянными*, если они *монотонны* и если интервал времени между соседними тактами является постоянной величиной.  
  
 High_resolution_clock является определением типа для steady_clock.  
  
## <a name="public-functions"></a>Открытые функции  
  
|Функция|Описание|  
|--------------|-----------------|  
|now|Возвращает текущее время как значение time_point.|  
  
## <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|`system_clock::is_steady`|Содержит `true`. Объект `steady_clock` — *постоянный*.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<chrono >  
  
 **Пространство имен:** std::chrono  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [Структура system_clock](../standard-library/system-clock-structure.md)

