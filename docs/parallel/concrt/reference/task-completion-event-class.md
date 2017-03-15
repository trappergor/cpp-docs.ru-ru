---
title: "Класс task_completion_event | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task_completion_event
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 2cd3e7381402cc65f3220010a71c969cda1c7e2d
ms.lasthandoff: 02/24/2017

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
|[task_completion_event конструктор](#ctor)|Создает объект `task_completion_event`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Set](#set)|Перегружен. Задает событие завершения задачи.|  
|[set_exception метод](#set_exception)|Перегружен. Распространяет исключение для всех задач, связанных с этим событием.|  
  
## <a name="remarks"></a>Примечания  
 Если требуется создать задачу, которая будет завершена и, тем самым, будет иметь запланированное продолжение для выполнения в определенный момент в будущем, следует использовать задачу, созданную из события завершения задачи. Объект `task_completion_event` должен быть того же типа, что и создаваемая задача. Вызов метода set для события завершения задачи со значением такого типа приведет к завершению соответствующей задачи и предоставит это значение как результат продолжения.  
  
 Если о событии завершения задачи не сообщается, все задачи, созданные из этого события, будут отменены при его уничтожении.  
  
 `task_completion_event` ведет себя как интеллектуальный указатель и должен передаваться по значению.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `task_completion_event`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>набор 

 Задает событие завершения задачи.  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>Параметры  
 `_Result`  
 Чтобы установить это событие с результат.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает `true` при успешной установке события. Он возвращает `false` Если событие уже установлено.  
  
### <a name="remarks"></a>Примечания  
 При наличии нескольких или одновременных вызовов для `set`, только первый вызов будет успешным, и его результат (если таковые имеются) будут храниться в событие завершения задачи. Остальные наборы учитываются, и метод возвращает значение false. При установке события завершения задачи все задачи создаваемых событий немедленно завершается, что ее продолжение, будут планироваться. Задача выполнения объектов, имеющих `_ResultType` не `void` передаст значение их продолжения.  
  
##  <a name="a-namesetexceptiona-setexception"></a><a name="set_exception"></a>set_exception 

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
  
##  <a name="a-namectora-taskcompletionevent"></a><a name="ctor"></a>task_completion_event 

 Создает объект `task_completion_event`.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

