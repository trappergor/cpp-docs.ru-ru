---
title: "Класс Agent | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::agent
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 640e1d66a879e8eb73428b50339d6a325cfd7cb2
ms.lasthandoff: 02/24/2017

---
# <a name="agent-class"></a>Класс agent
Класс, предназначенный для использования в качестве базового класса для всех независимых агентов. Он используется для скрытия состояния от других агентов и взаимодействия посредством передачи сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class agent;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор агента](#ctor)|Перегружен. Создает агент.|  
|[~ агента деструктор](#dtor)|Уничтожает агент.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Cancel-метод](#cancel)|Перемещает агент, либо от `agent_created` или `agent_runnable` состояния следует `agent_canceled` состояния.|  
|[Start-метод](#start)|Перемещает агент из `agent_created` состояние `agent_runnable` состояние и планирует ее выполнение.|  
|[состояние метода](#status)|Синхронный источник сведений о состоянии от агента.|  
|[status_port метод](#status_port)|Асинхронный источник сведений о состоянии от агента.|  
|[wait-метод](#wait)|Ожидает выполнения задач агента.|  
|[wait_for_all метод](#wait_for_all)|Ожидает, когда все указанные агенты для выполнения своих задач.|  
|[wait_for_one метод](#wait_for_one)|Ожидает один из указанных агентов для выполнения необходимых задач.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Done](#done)|Перемещает агент в `agent_done` состояние, указывающее, что агент завершился.|  
|[Метод Run](#run)|Представляет основную задача агента. `run`должны быть переопределены в производном классе и указывает, что агент должен делать после его запуска.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронных агентов](../../../parallel/concrt/asynchronous-agents.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `agent`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-agent"></a><a name="ctor"></a>агент 

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
 Среда выполнения использует планировщик по умолчанию, если вы не укажете `_PScheduler` или `_PGroup` параметры.  
  
##  <a name="a-namedtora-agent"></a><a name="dtor"></a>~ агента 

 Уничтожает агент.  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>Примечания  
 Это ошибка, чтобы удалить агент, который не находится в состоянии (либо `agent_done` или `agent_canceled`). Этого можно избежать, ожидания агента для достижения конечного состояния в деструкторе класса, который наследует от `agent` класса.  
  
##  <a name="a-namecancela-cancel"></a><a name="cancel"></a>Отмена 

 Перемещает агент, либо от `agent_created` или `agent_runnable` состояния следует `agent_canceled` состояния.  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если агент был отменен, `false` в противном случае. Невозможно отменить агент, если он уже был запущен или уже завершен.  
  
##  <a name="a-namedonea-done"></a><a name="done"></a>Договорились 

 Перемещает агент в `agent_done` состояние, указывающее, что агент завершился.  
  
```
bool done();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`При перемещении агента `agent_done` состояния, `false` в противном случае. Агент, который был отменен нельзя переместить `agent_done` состояния.  
  
### <a name="remarks"></a>Примечания  
 Этот метод должен вызываться в конце `run` завершения метода, когда вы знаете, выполнение ваших агента.  
  
##  <a name="a-nameruna-run"></a><a name="run"></a>Запуск 

 Представляет основную задача агента. `run`должны быть переопределены в производном классе и указывает, что агент должен делать после его запуска.  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Состояние агента изменяется на `agent_started` правой перед вызовом этого метода. Метод должен вызывать `done` на агент с соответствующим статусом перед возвратом и не может создавать исключения.  
  
##  <a name="a-namestarta-start"></a><a name="start"></a>Запуск 

 Перемещает агент из `agent_created` состояние `agent_runnable` состояние и планирует ее выполнение.  
  
```
bool start();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если агент запускается правильно, `false` в противном случае. Не удается запустить агент, который был отменен.  
  
##  <a name="a-namestatusa-status"></a><a name="status"></a>состояние 

 Синхронный источник сведений о состоянии от агента.  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текущее состояние агента. Обратите внимание, что это возвращаемое состояние может меняться сразу после возврата.  
  
##  <a name="a-namestatusporta-statusport"></a><a name="status_port"></a>status_port 

 Асинхронный источник сведений о состоянии от агента.  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает источник сообщения, который может отправлять сообщения о текущем состоянии агента.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Ожидание 

 Ожидает выполнения задач агента.  
  
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
  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если определенное время истекает до завершения агента.  
  
##  <a name="a-namewaitforalla-waitforall"></a><a name="wait_for_all"></a>wait_for_all 

 Ожидает, когда все указанные агенты для выполнения своих задач.  
  
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
 Указатель на массив состояний агентов. Каждое значение состояния будет представлять состояние соответствующего агента, при возврате метода.  
  
 `_Timeout`  
 Максимальное время ожидания в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояния.  
  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если определенное время истекает до завершения агента.  
  
##  <a name="a-namewaitforonea-waitforone"></a><a name="wait_for_one"></a>wait_for_one 

 Ожидает один из указанных агентов для выполнения необходимых задач.  
  
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
 Ссылка на переменную, где будут храниться состояние агента.  
  
 `_Index`  
 Ссылка на переменную, в которую будет помещен индекс агента.  
  
 `_Timeout`  
 Максимальное время ожидания в миллисекундах.  
  
### <a name="remarks"></a>Примечания  
 Задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояния.  
  
 Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если определенное время истекает до завершения агента.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

