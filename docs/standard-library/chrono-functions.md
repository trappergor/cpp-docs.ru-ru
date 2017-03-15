---
title: "Функции &lt;chrono&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9824bdc37d1ae2d1d3a8e42c727986fd2a194514
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-functions"></a>Функции &lt;chrono&gt;
||||  
|-|-|-|  
|[Функция duration_cast](#duration_cast_function)|[Функция time_point_cast](#time_point_cast_function)|  
  

##  <a name="a-namedurationcastfunctiona--durationcast-function"></a><a name="duration_cast_function"></a>Функция duration_cast  
 Приводит объект `duration` к указанному типу.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `duration` типа `To`, представляющий интервал времени `Dur`, который усекается, если должен соответствовать целевому типу.  
  
### <a name="remarks"></a>Примечания  
 Если `To` является экземпляром `duration`, эта функция не участвует в разрешении перегрузки.  
  
##  <a name="a-nametimepointcastfunctiona--timepointcast-function"></a><a name="time_point_cast_function"></a>Функция time_point_cast  
 Приводит объект [time_point](../standard-library/time-point-class.md) к указанному типу.  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `time_point`, который имеет длительность типа `To`.  
  
### <a name="remarks"></a>Примечания  
 Если `To` не является экземпляром [duration](../standard-library/duration-class.md), эта функция не участвует в разрешении перегрузки.  
  
## <a name="see-also"></a>См. также  
 [\<chrono>](../standard-library/chrono.md)


