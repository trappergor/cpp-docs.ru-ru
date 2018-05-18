---
title: Класс task_completion_event | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b22b77affd41aa60769543ae2bea2ed495084ae
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="taskcompletionevent-class"></a>Класс task_completion_event
Класс `task_completion_event` позволяет отложить выполнение задачи до выполнения условия или запустить задачу в ответ на внешнее событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```  
  
#### <a name="parameters"></a>Параметры  
 `_ResultType`  
 Тип результата данного класса `task_completion_event`.  
  
 `T`  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[task_completion_event](#ctor)|Создает объект `task_completion_event`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[set](#set)|Перегружен. Задает событие завершения задачи.|  
|[set_exception](#set_exception)|Перегружен. Распространяет исключение для всех задач, связанных с этим событием.|  
  
## <a name="remarks"></a>Примечания  
 Если требуется создать задачу, которая будет завершена и, тем самым, будет иметь запланированное продолжение для выполнения в определенный момент в будущем, следует использовать задачу, созданную из события завершения задачи. Объект `task_completion_event` должен быть того же типа, что и создаваемая задача. Вызов метода set для события завершения задачи со значением такого типа приведет к завершению соответствующей задачи и предоставит это значение как результат продолжения.  
  
 Если о событии завершения задачи не сообщается, все задачи, созданные из этого события, будут отменены при его уничтожении.  
  
 `task_completion_event` ведет себя как интеллектуальный указатель и должен передаваться по значению.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `task_completion_event`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="set"></a> Набор 

 Задает событие завершения задачи.  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>Параметры  
 `_Result`  
 Чтобы установить это событие с результат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает `true` успешную при задании события. Он возвращает `false` Если событие уже установлено.  
  
### <a name="remarks"></a>Примечания  
 При наличии нескольких или одновременных вызовов `set`, только первый вызов будет выполнен успешно, и его результат (если таковые имеются) будут храниться в событие завершения задачи. Остальные наборы учитываются, и метод будет возвращать значение false. При установке события завершения задачи всех задачах, созданных из немедленно завершит событие, которое ее продолжение, если таковые имеются, будет запланирована. Задача выполнения объектов, у которых `_ResultType` отличный от `void` передает значение их продолжениями.  
  
##  <a name="set_exception"></a> set_exception 

 Распространяет исключение для всех задач, связанных с этим событием.  
  
```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```  
  
### <a name="parameters"></a>Параметры  
 `_E`  
 `_Except`  
 `_ExceptionPtr`  
  
### <a name="return-value"></a>Возвращаемое значение  
  
##  <a name="ctor"></a> task_completion_event 

 Создает объект `task_completion_event`.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
