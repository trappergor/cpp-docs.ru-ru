---
title: "Класс recursive_timed_mutex | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 9
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
ms.openlocfilehash: 898661756cd21f362dc9d83dee6dab9b0c16fb8f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="recursivetimedmutex-class"></a>Класс recursive_timed_mutex
Представляет собой тип *мьютекса с ограничением по времени*. Используйте объекты этого типа для принудительного взаимного исключения с помощью ограниченной по времени блокировки в программе. В отличие от объектов типа [timed_mutex](../standard-library/timed-mutex-class.md), эффект вызова методов блокировки для объектов `recursive_timed_mutex` четко определен.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class recursive_timed_mutex;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[recursive_timed_mutex](#recursive_timed_mutex)|Создает объект `recursive_timed_mutex`, который не заблокирован.|  
|[Деструктор ~recursive_timed_mutex](#dtorrecursive_timed_mutex_destructor)|Освобождает все ресурсы, используемые объектом `recursive_timed_mutex`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|  
|[try_lock](#try_lock)|Попытки получить права владельца объекта `mutex` без блокировки.|  
|[try_lock_for](#try_lock_for)|Пытается получить права владельца `mutex` на заданный интервал времени.|  
|[try_lock_until](#try_lock_until)|Пытается получить права владельца `mutex` до заданного времени.|  
|[unlock](#unlock)|Освобождает права владения объектом `mutex`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<мьютекс >  
  
 **Пространство имен:** std  
  
##  <a name="lock"></a>  lock  
 Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение и предыдущая блокировка остается в силе.  
  
##  <a name="recursive_timed_mutex"></a>  Конструктор recursive_timed_mutex  
 Создает объект `recursive_timed_mutex`, который не заблокирован.  
  
```cpp  
recursive_timed_mutex();
```  
  
##  <a name="dtorrecursive_timed_mutex_destructor"></a>  Деструктор ~recursive_timed_mutex  
 Освобождает все ресурсы, используемые объектом `recursive_timed_mutex`.  
  
```cpp  
~recursive_timed_mutex();
```  
  
### <a name="remarks"></a>Примечания  
 Если при выполнении деструктора объект заблокирован, поведение не определено.  
  
##  <a name="try_lock"></a>  try_lock  
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если метод успешно получает права владельца `mutex` или если вызывающий поток уже владеет `mutex`; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает `true` и предыдущая блокировка остается в силе.  
  
##  <a name="try_lock_for"></a>  try_lock_for  
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Параметры  
 `Rel_time`  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если метод успешно получает права владельца `mutex` или если вызывающий поток уже владеет `mutex`; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение `true` и предыдущая блокировка остается в силе.  
  
##  <a name="try_lock_until"></a>  try_lock_until  
 Попытки получить права владельца объекта `mutex` без блокировки.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Параметры  
 `Abs_time`  
 Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если метод успешно получает права владельца `mutex` или если вызывающий поток уже владеет `mutex`; в противном случае — `false`.  
  
### <a name="remarks"></a>Примечания  
 Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение `true` и предыдущая блокировка остается в силе.  
  
##  <a name="unlock"></a>  unlock  
 Освобождает права владения объектом `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод освобождает владение `mutex` только если он вызван столько раз, сколько [lock](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for) и [try_lock_until](#try_lock_until) были успешно вызваны для объекта `recursive_timed_mutex`.  
  
 Если вызывающий поток не является владельцем `mutex`, поведение не определено.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




