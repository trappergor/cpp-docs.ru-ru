---
title: "Класс packaged_task | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::packaged_task
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
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
translationtype: Machine Translation
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: a54b1c9788ef60f63aafafc9125b09c449fde1b0
ms.lasthandoff: 02/24/2017

---
# <a name="packagedtask-class"></a>Класс packaged_task
Описывает *асинхронный поставщик*, который является оберткой вызова с сигнатурой вызова `Ty(ArgTypes...)`. Его *связанное асинхронное состояние* хранит копию его вызываемого объекта, помимо возможных результатов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор packaged_task::packaged_task](#packaged_task__packaged_task_constructor)|Создает объект `packaged_task`.|  
|[Деструктор packaged_task::~packaged_task](#packaged_task___dtorpackaged_task_destructor)|Уничтожает объект `packaged_task`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[packaged_task::get_future](#packaged_task__get_future_method)|Возвращает объект [future](../standard-library/future-class.md), который имеет то же связанное асинхронное состояние.|  
|[packaged_task::make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method)|Вызывает вызываемый объект, который хранится в связанном асинхронном состоянии и атомарно сохраняет возвращаемое значение.|  
|[packaged_task::reset](#packaged_task__reset_method)|Заменяет связанное асинхронное состояние.|  
|[packaged_task::swap](#packaged_task__swap_method)|Меняет местами связанное асинхронное состояние с состоянием указанного объекта.|  
|[packaged_task::valid](#packaged_task__valid_method)|Указывает, имеет ли объект связанное асинхронное состояние.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[packaged_task::operator=](#packaged_task__operator_eq)|Передает связанное асинхронное состояние из указанного объекта.|  
|[packaged_task::operator()](#packaged_task__operator__)|Вызывает вызываемый объект, который хранится в связанном асинхронном состоянии, атомарно сохраняет возвращаемое значение и устанавливает состояние в значение *ready*.|  
|[packaged_task::operator bool](#packaged_task__operator_bool)|Указывает, имеет ли объект связанное асинхронное состояние.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
##  <a name="a-namepackagedtaskgetfuturemethoda--packagedtaskgetfuture"></a><a name="packaged_task__get_future_method"></a>  packaged_task::get_future  
 Возвращает объект типа `future<Ty>`, который имеет то же самое *связанное асинхронное состояние*.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Примечания  
 Если объект `packaged_task` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если этот метод уже был вызван для объекта `packaged_task`, который имеет то же самое асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `future_already_retrieved`.  
  
##  <a name="a-namepackagedtaskmakereadyatthreadexitmethoda--packagedtaskmakereadyatthreadexit"></a><a name="packaged_task__make_ready_at_thread_exit_method"></a>  packaged_task::make_ready_at_thread_exit  
 Вызывает вызываемый объект, который хранится в *связанном асинхронном состоянии* и атомарно сохраняет возвращаемое значение.  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>Примечания  
 Если объект `packaged_task` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если этот метод или [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) уже был вызван для объекта `packaged_task`, который имеет то же самое связанное асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.  
  
 В противном случае этот оператор вызывает `INVOKE(fn, args..., Ty)`, где *fn* — вызываемый объект, который хранится в связанном асинхронном состоянии. Любое возвращаемое значение атомарно сохраняется как возвращенный результат связанного асинхронного состояния.  
  
 В отличие от [packaged_task:: operator()](#packaged_task__operator__) связанное асинхронное состояние не устанавливается в `ready`, пока не будут уничтожены все локальные объекты потока в вызывающем потоке. Обычно потоки, которые заблокированы в связанном асинхронном состоянии, не разблокируются до выхода из вызывающего потока.  
  
##  <a name="a-namepackagedtaskoperatoreqa--packagedtaskoperator"></a><a name="packaged_task__operator_eq"></a>  packaged_task::operator=  
 Передает *связанное асинхронное состояние* из указанного объекта.  
  
```
packaged_task& operator=(packaged_task&& Right);
```  
  
### <a name="parameters"></a>Параметры  
 `Right`  
 Объект `packaged_task`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `*this`  
  
### <a name="remarks"></a>Примечания  
 После операции `Right` больше не имеет связанного асинхронного состояния.  
  
##  <a name="a-namepackagedtaskoperatora--packagedtaskoperator"></a><a name="packaged_task__operator__"></a>  packaged_task::operator()  
 Вызывает вызываемый объект, который хранится в *связанном асинхронном состоянии*, атомарно сохраняет возвращаемое значение и устанавливает состояние в значение *ready*.  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>Примечания  
 Если объект `packaged_task` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.  
  
 Если этот метод или [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) уже был вызван для объекта `packaged_task`, который имеет то же самое связанное асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.  
  
 В противном случае этот оператор вызывает `INVOKE(fn, args..., Ty)`, где *fn* — вызываемый объект, который хранится в связанном асинхронном состоянии. Любое возвращаемое значение атомарно сохраняется как возвращенный результат связанного асинхронного состояния, и состояние устанавливается в значение ready. В результате все потоки, которые заблокированы на связанном асинхронном состоянии, разблокируются.  
  
##  <a name="a-namepackagedtaskoperatorboola--packagedtaskoperator-bool"></a><a name="packaged_task__operator_bool"></a>  packaged_task::operator bool  
 Указывает, имеет ли объект `associated asynchronous state`.  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объект имеет связанное асинхронное состояние; в противном случае — значение `false`.  
  
##  <a name="a-namepackagedtaskpackagedtaskconstructora--packagedtaskpackagedtask-constructor"></a><a name="packaged_task__packaged_task_constructor"></a>  Конструктор packaged_task::packaged_task  
 Создает объект `packaged_task`.  
  
```
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```  
  
### <a name="parameters"></a>Параметры  
 `Right`  
 Объект `packaged_task`.  
  
 `alloc`  
 Распределитель памяти. Дополнительные сведения см. в разделе [\<allocators>](../standard-library/allocators-header.md).  
  
 `fn`  
 Объект функции.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает объект `packaged_task`, который не имеет *связанного асинхронного состояния*.  
  
 Второй конструктор создает объект `packaged_task` и передает связанное асинхронное состояние из `Right`. После операции `Right` больше не имеет связанного асинхронного состояния.  
  
 Третий конструктор создает объект `packaged_task`, который имеет копию `fn`, сохраненную в его связанном асинхронном состоянии.  
  
 Четвертый конструктор создает объект `packaged_task`, который имеет копию `fn`, сохраненную в его связанном асинхронном состоянии, и использует `alloc` для выделения памяти.  
  
##  <a name="a-namepackagedtaskdtorpackagedtaskdestructora--packagedtaskpackagedtask-destructor"></a><a name="packaged_task___dtorpackaged_task_destructor"></a> Деструктор packaged_task::~packaged_task  
 Уничтожает объект `packaged_task`.  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>Примечания  
 Если *связанное асинхронное состояние* отлично от значения *ready*, деструктор сохраняет исключение [future_error](../standard-library/future-error-class.md) с кодом ошибки `broken_promise` в качестве результата в связанное асинхронное состояние. Все потоки, которые заблокированы на связанное асинхронное состояние, разблокируются.  
  
##  <a name="a-namepackagedtaskresetmethoda--packagedtaskreset"></a><a name="packaged_task__reset_method"></a>  packaged_task::reset  
 Использует новое *связанное асинхронное состояние* для замены существующего связанного асинхронного состояния.  
  
```
void reset();
```  
  
### <a name="remarks"></a>Примечания  
 По сути, этот метод выполняет `*this = packaged_task(move(fn))`, где *fn* является объектом функции, который хранится в связанном асинхронном состоянии для данного объекта. Таким образом, состояние объекта очищается и [get_future](#packaged_task__get_future_method), [operator()](#packaged_task__operator__) и [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) можно вызывать как на вновь созданный объект.  
  
##  <a name="a-namepackagedtaskswapmethoda--packagedtaskswap"></a><a name="packaged_task__swap_method"></a>  packaged_task::swap  
 Меняет местами связанное асинхронное состояние с состоянием указанного объекта.  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>Параметры  
 `Right`  
 Объект `packaged_task`.  
  
##  <a name="a-namepackagedtaskvalidmethoda--packagedtaskvalid"></a><a name="packaged_task__valid_method"></a>  packaged_task::valid  
 Указывает, имеет ли объект `associated asynchronous state`.  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если объект имеет связанное асинхронное состояние; в противном случае — значение `false`.  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




