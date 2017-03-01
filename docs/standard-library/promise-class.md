---
title: "Класс promise | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::promise
dev_langs:
- C++
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: ad79ecc3497182a451ef85ea53c8ec5603fdca69
ms.lasthandoff: 02/24/2017

---
# <a name="promise-class"></a>Класс promise
Описывает *асинхронный поставщик*.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
class promise;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор promise::promise](#promise__promise_constructor)|Создает объект `promise`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[promise::get_future](#promise__get_future_method)|Возвращает [future](../standard-library/future-class.md), связанный с этим объектом promise.|  
|[promise::set_exception](#promise__set_exception_method)|Атомарно устанавливает результат этого объекта promise для обозначения исключения.|  
|[promise::set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method)|Атомарно устанавливает результат этого объекта promise для обозначения исключения и доставляет уведомление только после того, как все локальные объекты в текущем потоке уничтожены (обычно при выходе из потока).|  
|[promise::set_value](#promise__set_value_method)|Атомарно устанавливает результат этого объекта promise для обозначения значения.|  
|[promise::set_value_at_thread_exit](#promise__set_value_at_thread_exit_method)|Атомарно устанавливает результат этого объекта promise для обозначения значения и доставляет уведомление только после того, как все локальные объекты в текущем потоке уничтожены (обычно при выходе из потока).|  
|[promise::swap](#promise__swap_method)|Выполняет обмен *связанного асинхронного состояния* этого объекта promise с состоянием указанного объекта promise.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[promise::operator=](#promise__operator_eq)|Назначение общего состояния этого объекта promise.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `promise`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
##  <a name="a-namepromisegetfuturemethoda--promisegetfuture"></a><a name="promise__get_future_method"></a>  promise::get_future  
 Возвращает объект [future](../standard-library/future-class.md), который имеет то же самое *связанное асинхронное состояние*, что и данный объект promise.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Примечания  
 Если объект promise пустой, этот метод выдает [future_error](../standard-library/future-error-class.md) с [error_code](../standard-library/error-code-class.md) `no_state`.  
  
 Если этот метод уже вызывался для объекта promise с тем же самым связанным асинхронным состоянием, метод выдает `future_error` с `error_code` `future_already_retrieved`.  
  
##  <a name="a-namepromiseoperatoreqa--promiseoperator"></a><a name="promise__operator_eq"></a>  promise::operator=  
 Передает *связанное асинхронное состояние* от указанного объекта `promise`.  
  
```
promise& operator=(promise&& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `promise`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `*this`  
  
### <a name="remarks"></a>Примечания  
 Этот оператор передает связанное асинхронное состояние от `Other`. После передачи `Other` получает значение *empty*.  
  
##  <a name="a-namepromisepromiseconstructora--promisepromise-constructor"></a><a name="promise__promise_constructor"></a>  Конструктор promise::promise  
 Создает объект `promise`.  
  
```
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Al`  
 Распределитель памяти. Более подробную информацию см. в разделе [\<allocators>](../standard-library/allocators-header.md).  
  
 `Other`  
 Объект `promise`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает *пустой*`promise` объект.  
  
 Второй конструктор создает пустой объект `promise` и использует `Al` для распределения памяти.  
  
 Третий конструктор создает объект `promise` и передает асинхронное состояние из `Other`, затем оставляет `Other` пустым.  
  
##  <a name="a-namepromisesetexceptionmethoda--promisesetexception"></a><a name="promise__set_exception_method"></a>  promise::set_exception  
 Автоматически сохраняет исключение в качестве результата объекта `promise` и устанавливает *связанное асинхронное состояние* в значение *ready*.  
  
```
void set_exception(exception_ptr Exc);
```  
  
### <a name="parameters"></a>Параметры  
 `Exc`  
 [Exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), который сохраняется этим методом как результат исключения.  
  
### <a name="remarks"></a>Примечания  
 Если объект `promise` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если `set_exception`, [set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method), [set_value](#promise__set_value_method) или [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) уже вызывались для объекта `promise`, который имеет то же самое связанное асинхронное состояние, то этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.  
  
 В результате работы этого метода все потоки, которые заблокированы на связанном асинхронном состоянии, разблокируются.  
  
##  <a name="a-namepromisesetexceptionatthreadexitmethoda--promisesetexceptionatthreadexit"></a><a name="promise__set_exception_at_thread_exit_method"></a>  promise::set_exception_at_thread_exit  
 Атомарно устанавливает результат `promise` для указания исключения, доставляя уведомление только после того, как все локальные объекты в текущем потоке уничтожены (обычно при завершении потока).  
  
```
void set_exception_at_thread_exit(exception_ptr Exc);
```  
  
### <a name="parameters"></a>Параметры  
 `Exc`  
 [Exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), который сохраняется этим методом как результат исключения.  
  
### <a name="remarks"></a>Примечания  
 Если объект promise не имеет *связанного асинхронного состояния*, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если [set_exception](#promise__set_exception_method), `set_exception_at_thread_exit`, [set_value](#promise__set_value_method) или [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) уже вызывались для объекта `promise`, имеющего то же самое связанное асинхронное состояние, то этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.  
  
 В отличие от [set_exception](#promise__set_exception_method) этот метод не устанавливает связанное асинхронное состояние в значение ready до тех пор, пока не будут уничтожены все локальные объекты в текущем потоке. Обычно потоки, которые заблокированы в связанном асинхронном состоянии, не разблокируются до завершения текущего потока.  
  
##  <a name="a-namepromisesetvaluemethoda--promisesetvalue"></a><a name="promise__set_value_method"></a>  promise::set_value  
 Атомарно сохраняет значение в виде результата этого объекта `promise` и устанавливает *связанное асинхронное состояние* в значение *ready*.  
  
```
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```  
  
### <a name="parameters"></a>Параметры  
 `Val`  
 Значение, которое будет сохранено в качестве результата.  
  
### <a name="remarks"></a>Примечания  
 Если объект `promise` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если [set_exception](#promise__set_exception_method), [set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method) `set_value` или [set_value_at_thread_exit](#promise__set_value_at_thread_exit_method) уже вызывались для объекта `promise`, имеющего то же самое связанное асинхронное состояние, то этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.  
  
 В результате работы этого метода все потоки, которые заблокированы на связанном асинхронном состоянии, разблокируются.  
  
 Первый метод также выдает любое исключение, вызванное при копировании `Val` в связанное асинхронное состояние. В этой ситуации связанное асинхронное состояние не устанавливается в значение ready.  
  
 Второй метод также выдает любое исключение, вызванное при перемещении `Val` в связанное асинхронное состояние. В этой ситуации связанное асинхронное состояние не устанавливается в значение ready.  
  
 Для частичной специализации `promise<Ty&>` сохраненное значение по сути является ссылкой на `Val`.  
  
 Для специализации `promise<void>` сохраненные значения не существуют.  
  
##  <a name="a-namepromisesetvalueatthreadexitmethoda--promisesetvalueatthreadexit"></a><a name="promise__set_value_at_thread_exit_method"></a>  promise::set_value_at_thread_exit  
 Атомарно сохраняет значение в качестве результата этого объекта `promise`.  
  
```
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```  
  
### <a name="parameters"></a>Параметры  
 `Val`  
 Значение, которое будет сохранено в качестве результата.  
  
### <a name="remarks"></a>Примечания  
 Если объект promise не имеет *связанного асинхронного состояния*, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если [set_exception](#promise__set_exception_method), [set_exception_at_thread_exit](#promise__set_exception_at_thread_exit_method), [set_value](#promise__set_value_method) или `set_value_at_thread_exit` уже вызывались для объекта `promise`, имеющего то же самое связанное асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.  
  
 В отличие от `set_value` связанное асинхронное состояние не устанавливается в значение ready до тех пор, пока все локальные объекты текущего потока не будут уничтожены. Обычно потоки, которые заблокированы в связанном асинхронном состоянии, не разблокируются до завершения текущего потока.  
  
 Первый метод также выдает любое исключение, вызванное при копировании `Val` в связанное асинхронное состояние.  
  
 Второй метод также выдает любое исключение, вызванное при перемещении `Val` в связанное асинхронное состояние.  
  
 Для частичной специализации `promise<Ty&>` сохраненное значение по сути является ссылкой на `Val`.  
  
 Для специализации `promise<void>` сохраненные значения не существуют.  
  
##  <a name="a-namepromiseswapmethoda--promiseswap"></a><a name="promise__swap_method"></a>  promise::swap  
 Обменивает *связанное асинхронное состояние* данного объекта promise с состоянием указанного объекта.  
  
```
void swap(promise& Other) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Other`  
 Объект `promise`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)




 


