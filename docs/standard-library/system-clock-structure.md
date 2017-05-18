---
title: "Структура system_clock | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
dev_langs:
- C++
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 053b2930d25bb7b1ec073764801530860511ac1b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="systemclock-structure"></a>Структура system_clock
Представляет *тип clock*, использующий данные системных часов в реальном времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct system_clock;  
```  
  
## <a name="remarks"></a>Примечания  
 *Тип clock* используется для получения текущего времени в формате UTC. Этот тип реализует экземпляр класса [duration](../standard-library/duration-class.md) и шаблон класса [time_point](../standard-library/time-point-class.md), а также определяет статическую функцию-член `now()`, которая возвращает время.  
  
 Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда меньше значения, возвращаемого при последующих вызовах `now()`, или равно ему.  
  
 Часы считаются *постоянными*, если они *монотонны* и интервал времени между соседними тактами является постоянной величиной.  
  
 В этой реализации `system_clock` является синонимом `high_resolution_clock`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`system_clock::duration`|Синоним для `duration<rep, period>`.|  
|`system_clock::period`|Синоним для типа, который используется для представления тактового периода при автономном создании экземпляра `duration`.|  
|`system_clock::rep`|Синоним для типа, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|  
|`system_clock::time_point`|Синоним для `time_point<Clock, duration>`, где `Clock` является синонимом для самого типа часов или для другого типа часов, настроенного на ту же эпоху и имеющего тот же вложенный тип `duration`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[from_time_t](#from_time_t)|Статический. Возвращает объект `time_point`, наиболее точно соответствующий указанному времени.|  
|[Теперь](#now)|Статический. Возвращает текущее время.|  
|[to_time_t](#to_time_t)|Статический. Возвращает объект `time_t`, наиболее точно соответствующий указанному объекту `time_point`.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Константа system_clock::is_monotonic](#is_monotonic_constant)|Указывает, являются ли часы монотонными.|  
|[Константа system_clock::is_steady](#is_steady_constant)|Указывает, являются ли часы постоянными.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<chrono >  
  
 **Пространство имен:** std::chrono  
  
##  <a name="from_time_t"></a>system_clock::from_time_t
 Статический метод, возвращающий [time_point](../standard-library/time-point-class.md), которая наиболее точно соответствует времени, представляемому `Tm`.  
  
```  
static time_point from_time_t(time_t Tm) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `Tm`  
 Объект [time_t](../c-runtime-library/standard-types.md).  
  
##  <a name="is_monotonic_constant"></a>  Константа system_clock::is_monotonic  
 Статическое значение, указывающее, являются ли часы монотонными.  
  
```  
static const bool is_monotonic = false;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В данной реализации `system_clock::is_monotonic` всегда возвращает `false`.  
  
### <a name="remarks"></a>Примечания  
 Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда меньше значения, возвращаемого при последующих вызовах `now()`, или равно ему.  
  
##  <a name="is_steady_constant"></a> Константа system_clock::is_steady  
 Статическое значение, указывающее, являются ли часы *постоянными*.  
  
```  
static const bool is_steady = false;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В данной реализации `system_clock::is_steady` всегда возвращает `false`.  
  
### <a name="remarks"></a>Примечания  
 Часы считаются *постоянными*, если они [монотонны](#is_monotonic_constant) и интервал времени между соседними тактами является постоянной величиной.  
  
##  <a name="now"></a>system_clock::Now
 Статический метод, который возвращает текущее время.  
  
```  
static time_point now() noexcept;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [time_point](../standard-library/time-point-class.md), представляющий текущее время.  
  
##  <a name="to_time_t"></a>system_clock::to_time_t
 Статический метод, возвращающий значение [time_t](../c-runtime-library/standard-types.md), которое наиболее точно соответствует времени, представляемому `Time`.  
  
```  
static time_t to_time_t(const time_point& Time) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `Time`  
 Объект [time_point](../standard-library/time-point-class.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [Структура steady_clock](../standard-library/steady-clock-struct.md)

