---
title: "Функции &lt;thread&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: de302b9a2d971b2a39d4ce775799f27dd7244a5c
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt-functions"></a>Функции &lt;thread&gt;
||||  
|-|-|-|  
|[get_id](#get_id_function)|[sleep_for](#sleep_for_function)|[sleep_until](#sleep_until_function)|  
|[swap](#swap_function)|[yield](#yield_function)|  
  
##  <a name="a-namegetidfunctiona--getid"></a><a name="get_id_function"></a>  get_id  
 Уникально идентифицирует текущий поток выполнения.  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект типа [thread::id](../standard-library/thread-class.md), который уникально идентифицирует текущий поток выполнения.  
  
##  <a name="a-namesleepforfunctiona--sleepfor"></a><a name="sleep_for_function"></a>  sleep_for  
 Блокирует вызывающий поток.  
  
```  
template <class Rep,  
class Period>  
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Параметры  
 `Rel_time`  
 Объект [duration](../standard-library/duration-class.md), задающий интервал времени.  
  
### <a name="remarks"></a>Примечания  
 Функция блокирует вызывающий поток по меньшей мере на время, заданное `Rel_time`. Эта функция не вызывает исключений.  
  
##  <a name="a-namesleepuntilfunctiona--sleepuntil"></a><a name="sleep_until_function"></a>  sleep_until  
 Блокирует вызывающий поток по крайней мере до указанного времени.  
  
```  
template <class Clock, class Duration>  
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```  
  
### <a name="parameters"></a>Параметры  
 `Abs_time`  
 Представляет момент времени.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не вызывает исключений.  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a>  swap  
 Меняет местами состояния двух объектов `thread`.  
  
```  
void swap(thread& Left, thread& Right) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `Left`  
 Левый объект `thread`.  
  
 `Right`  
 Правой объект `thread`.  
  
### <a name="remarks"></a>Примечания  
 Функция вызывает `Left.swap(Right)`.  
  
##  <a name="a-nameyieldfunctiona--yield"></a><a name="yield_function"></a>  yield  
 Сигнализирует операционной системе, что необходимо запустить другие потоки, даже если в обычной ситуации текущий поток продолжал бы выполняться.  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>См. также  
 [\<thread>](../standard-library/thread.md)


