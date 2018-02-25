---
title: "Класс Agent | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a4617007525fdd924dce7b09f1d351c7c18cc96
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="agent-class"></a>Класс agent
Класс, предназначенный для использования в качестве базового класса для всех независимых агентов. Он используется для скрытия состояния от других агентов и взаимодействия посредством передачи сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class agent;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[agent](#ctor)|Перегружен. Создает агент.|  
|[~ агента деструктор](#dtor)|Уничтожает агент.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[cancel](#cancel)|Перемещает агент, либо из `agent_created` или `agent_runnable` состояния следует `agent_canceled` состояния.|  
|[start](#start)|Перемещает агент из `agent_created` состояние `agent_runnable` состояние и планирует его для выполнения.|  
|[status](#status)|Синхронный источник сведений о состоянии от агента.|  
|[status_port](#status_port)|Асинхронный источник сведений о состоянии от агента.|  
|[Ожидание](#wait)|Ожидает, пока агент для выполнения необходимых задач.|  
|[wait_for_all](#wait_for_all)|Ожидает, когда все агенты, указанный для завершения своих задач.|  
|[wait_for_one](#wait_for_one)|Ожидает завершения любого из указанных агентов для выполнения необходимых задач.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[done](#done)|Перемещает агент в `agent_done` состоянии, указывающее, что агент был выполнен.|  
|[run](#run)|Представляет основную задача агента. `run` должен быть переопределен в производном классе и указывает, что агент должен делать после его запуска.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронных агентов](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `agent`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a> Агент 

 Создает агент.  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>Параметры  
 `_PScheduler`  
 `Scheduler` Объекта, в котором запланировано выполнение задания агента.  
  
 `_PGroup`  
 `ScheduleGroup` Объекта, в котором запланировано выполнение задания агента. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не укажете `_PScheduler` или `_PGroup` параметров.  
  
##  <a name="dtor"></a> ~ агента 

 Уничтожает агент.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Примечания  
 Это ошибка, чтобы удалить агент, который не находится в состоянии (либо `agent_done` или `agent_canceled`). Этого можно избежать, если ожидание агента для достижения конечного состояния в деструкторе класса, который наследует от `agent` класса.  
  
##  <a name="cancel"></a> Отмена 

 Перемещает агент, либо из `agent_created` или `agent_runnable` состояния следует `agent_canceled` состояния.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если агент был отменен, `false` в противном случае. Агент нельзя отменить, если он уже запущен или уже завершен.  
  
##  <a name="done"></a> Договорились 

 Перемещает агент в `agent_done` состоянии, указывающее, что агент был выполнен.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если агент был перемещен `agent_done` состояния, `false` в противном случае. Не удалось переместить агент, который был отменен `agent_done` состояния.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться в конце `run` завершения метода, если известно выполнения агента.  
  
##  <a name="run"></a> run 

 Представляет основную задача агента. `run` должен быть переопределен в производном классе и указывает, что агент должен делать после его запуска.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Состояние агента изменяется на `agent_started` правой перед вызовом этого метода. Метод следует вызвать `done` на агент с соответствующим статусом перед возвратом и не может создавать исключения.  
  
##  <a name="start"></a> Запуск 

 Перемещает агент из `agent_created` состояние `agent_runnable` состояние и планирует его для выполнения.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если агент запускается правильно, `false` в противном случае. Не удается запустить агент, который был отменен.  
  
##  <a name="status"></a> Состояние 

 Синхронный источник сведений о состоянии от агента.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее состояние агента. Обратите внимание, что это возвращаемое состояние может меняться сразу после возврата.  
  
##  <a name="status_port"></a> status_port 

 Асинхронный источник сведений о состоянии от агента.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает источник сообщения, который может отправлять сообщения о текущем состоянии агента.  
  
##  <a name="wait">Ожидание</a> 

 Ожидает, пока агент для выполнения необходимых задач.  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `_PAgent`  
 Указатель на ожидаемый агент.  
  
 `_Timeout`  
 Максимальное время ожидания в миллисекундах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `agent_status` При завершении ожидания агента. Это может быть `agent_canceled` или `agent_done`.  
  
### <a name="remarks"></a>Примечания  
 Задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояния.  
  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если определенное время истекает до завершения его задачи агента.  
  
##  <a name="wait_for_all"></a> wait_for_all 

 Ожидает, когда все агенты, указанный для завершения своих задач.  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
 Число указателей агента, присутствующих в массиве `_PAgents`.  
  
 `_PAgents`  
 Массив указателей на агентов для ожидания.  
  
 `_PStatus`  
 Указатель на массив состояний агентов. Каждое значение состояния будет представлять состояние соответствующего агента, когда метод возвращает.  
  
 `_Timeout`  
 Максимальное время ожидания в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояния.  
  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если определенное время истекает до завершения его задачи агента.  
  
##  <a name="wait_for_one"></a> wait_for_one 

 Ожидает завершения любого из указанных агентов для выполнения необходимых задач.  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>Параметры  
 `count`  
 Число указателей агента, присутствующих в массиве `_PAgents`.  
  
 `_PAgents`  
 Массив указателей на агентов для ожидания.  
  
 `_Status`  
 Ссылка на переменную, где будет размещаться состояние агента.  
  
 `_Index`  
 Ссылка на переменную, которую будет помещен индекс агента.  
  
 `_Timeout`  
 Максимальное время ожидания в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояния.  
  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если определенное время истекает до завершения его задачи агента.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
