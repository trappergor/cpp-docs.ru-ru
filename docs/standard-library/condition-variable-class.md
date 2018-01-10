---
title: "Класс condition_variable | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs: C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.workload: cplusplus
ms.openlocfilehash: 3b51ec2810ddb982d53c3073bdf860b26100859d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="conditionvariable-class"></a>Класс condition_variable
Класс `condition_variable` используется для ожидания события при наличии `mutex` типа `unique_lock<mutex>`. Объекты этого типа могут иметь лучшую производительность, чем объекты типа [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
class condition_variable;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[condition_variable](#condition_variable)|Создает объект `condition_variable`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[native_handle](#native_handle)|Возвращает тип реализации, представляющий дескриптор condition_variable.|  
|[notify_all](#notify_all)|Разблокирует все потоки, которые ожидают объект `condition_variable`.|  
|[notify_one](#notify_one)|Разблокирует один из потоков, которые ожидают объект `condition_variable`.|  
|[Ожидание](#wait)|Блокирует поток.|  
|[wait_for](#wait_for)|Блокирует поток и задает интервал времени, после которого поток разблокируется.|  
|[wait_until](#wait_until)|Блокирует поток и задает максимальный момент времени, в который поток разблокируется.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<condition_variable >  
  
 **Пространство имен:** std  
  
##  <a name="condition_variable"></a>  Конструктор condition_variable::condition_variable  
 Создает объект `condition_variable`.  
  
```
condition_variable();
```  
  
### <a name="remarks"></a>Примечания  
 При недостатке памяти этот конструктор вызывает объект [system_error](../standard-library/system-error-class.md), имеющий код ошибки `not_enough_memory`. Если объект не может быть создан из-за недоступности некоторых других ресурсов, конструктор создает объект `system_error`, имеющий код ошибки `resource_unavailable_try_again`.  
  
##  <a name="native_handle"></a>  condition_variable::native_handle  
 Возвращает тип реализации, представляющий дескриптор condition_variable.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `native_handle_type` определяется как указатель на внутренние структуры данных среды выполнения с параллелизмом.  
  
##  <a name="notify_all"></a>  condition_variable::notify_all  
 Разблокирует все потоки, которые ожидают объект `condition_variable`.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="notify_one"></a>  condition_variable::notify_one  
 Разблокирует один из потоков, которые ожидают объект `condition_variable`.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="wait"></a>  condition_variable::wait  
 Блокирует поток.  
  
```
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Параметры  
 `Lck`  
 Объект [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Pred`  
 Любое выражение, возвращающее значение `true` или `false`.  
  
### <a name="remarks"></a>Примечания  
 Первый метод блокируется до оповещения объекта `condition_variable` путем вызова [notify_one](#notify_one) или [notify_all](#notify_all). Он может также ложно активироваться.  
  
 Второй метод фактически выполняет следующий код.  
  
```cpp  
while(!Pred())
    wait(Lck);
```    
  
##  <a name="wait_for"></a>  condition_variable::wait_for  
 Блокирует поток и задает интервал времени, после которого поток разблокируется.  
  
```
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Параметры  
 `Lck`  
 Объект [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Rel_time`  
 Объект `chrono::duration`, указывающий количество времени до активации потока.  
  
 `Pred`  
 Любое выражение, возвращающее значение `true` или `false`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый метод возвращает `cv_status::timeout`, если ожидание прекращается, когда прошло `Rel_time`. В противном случае метод возвращает значение `cv_status::no_timeout`.  
  
 Второй метод возвращает значение `Pred`.  
  
### <a name="remarks"></a>Примечания  
 Первый метод блокируется до оповещения объекта `condition_variable` путем вызова [notify_one](#notify_one) или [notify_all](#notify_all), или до завершения временного интервала `Rel_time`. Он может также ложно активироваться.  
  
 Второй метод фактически выполняет следующий код.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="wait_until"></a>  condition_variable::wait_until  
 Блокирует поток и задает максимальный момент времени, в который поток разблокируется.  
  
```
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time, 
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Параметры  
 `Lck`  
 Объект [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Abs_time`  
 Объект [chrono::time_point](../standard-library/time-point-class.md).  
  
 `Pred`  
 Любое выражение, возвращающее значение `true` или `false`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Методы, возвращающие тип `cv_status`, возвращают `cv_status::timeout`, если ожидание прекращается, когда истекает `Abs_time`. В противном случае эти методы возвращают `cv_status::no_timeout`.  
  
 Методы, возвращающие `bool` возвращают значение `Pred`.  
  
### <a name="remarks"></a>Примечания  
 Первый метод блокируется до оповещения объекта `condition_variable` путем вызова [notify_one](#notify_one) или [notify_all](#notify_all)`Abs_time`. Он может также ложно активироваться.  
  
 Второй метод фактически выполняет следующий код.  
  
```cpp  
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 Третий и четвертый методы используют указатель на объект типа `xtime` для замены объекта `chrono::time_point`. Объект `xtime` задает максимальное время ожидания сигнала.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)



