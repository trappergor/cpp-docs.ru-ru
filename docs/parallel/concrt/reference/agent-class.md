---
title: Класс agent
ms.date: 11/04/2016
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
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
ms.openlocfilehash: 98ad5f817361d8410e5a60648fb23baec06c42d7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289147"
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
|[Агент](#ctor)|Перегружен. Создает агент.|
|[~ агента деструктор](#dtor)|Уничтожает агент.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Отмена](#cancel)|Перемещает агент из либо `agent_created` или `agent_runnable` состояния следует `agent_canceled` состояния.|
|[start](#start)|Перемещает агента `agent_created` состояние `agent_runnable` состояния и планирует его выполнение.|
|[status](#status)|Синхронный источник сведений о состоянии от агента.|
|[status_port](#status_port)|Асинхронный источник сведений о состоянии от агента.|
|[wait](#wait)|Ожидает, пока агент для выполнения необходимых задач.|
|[wait_for_all](#wait_for_all)|Ожидает, когда все агенты, указанный для выполнения своих задач.|
|[wait_for_one](#wait_for_one)|Ожидает в течение любого из указанных агентов для выполнения необходимых задач.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[Договорились](#done)|Перемещает агент в `agent_done` состоянию с указанием, что агент завершено.|
|[run](#run)|Представляет основную задачу агента. `run` должен быть переопределен в производном классе и указывает, что агент должен делать после его запуска.|

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

*_PScheduler*<br/>
`Scheduler` Объекта, в котором запланировано выполнение задания агента.

*_PGroup*<br/>
`ScheduleGroup` Объекта, в котором запланировано выполнение задания агента. Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Примечания

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PGroup` .

##  <a name="dtor"></a> ~ агента

Уничтожает агент.

```
virtual ~agent();
```

### <a name="remarks"></a>Примечания

Является ошибкой, чтобы удалить агент, который не находится в состоянии (либо `agent_done` или `agent_canceled`). Этого можно избежать, если ожидание агента для достижения конечного состояния в деструкторе класса, который наследует от `agent` класса.

##  <a name="cancel"></a> Отмена

Перемещает агент из либо `agent_created` или `agent_runnable` состояния следует `agent_canceled` состояния.

```
bool cancel();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если агент был отменен, **false** в противном случае. Агент нельзя отменить, если он уже был запущен или уже завершена.

##  <a name="done"></a> Договорились

Перемещает агент в `agent_done` состоянию с указанием, что агент завершено.

```
bool done();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** агент при перемещении к `agent_done` состояние, **false** в противном случае. Невозможно переместить агент, который был отменен `agent_done` состояния.

### <a name="remarks"></a>Примечания

Этот метод должен вызываться в конце `run` завершения метода, когда вы знаете выполнения агента.

##  <a name="run"></a> запустить

Представляет основную задачу агента. `run` должен быть переопределен в производном классе и указывает, что агент должен делать после его запуска.

```
virtual void run() = 0;
```

### <a name="remarks"></a>Примечания

Состояние агента изменится на `agent_started` правой кнопкой мыши перед вызовом этого метода. Метод должен вызывать `done` агента с соответствующим статусом перед возвратом и не может создавать исключения.

##  <a name="start"></a> Запуск

Перемещает агента `agent_created` состояние `agent_runnable` состояния и планирует его выполнение.

```
bool start();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если агент запускается правильно, **false** в противном случае. Невозможно запустить агент, который был отменен.

##  <a name="status"></a> состояние

Синхронный источник сведений о состоянии от агента.

```
agent_status status();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее состояние агента. Обратите внимание на то, что это возвращаемое состояние может изменить сразу после возврата.

##  <a name="status_port"></a> status_port

Асинхронный источник сведений о состоянии от агента.

```
ISource<agent_status>* status_port();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает источник сообщения, который можно отправлять сообщения о текущем состоянии агента.

##  <a name="wait"></a> Подождите

Ожидает, пока агент для выполнения необходимых задач.

```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_PAgent*<br/>
Указатель на агент для ожидания.

*_Timeout*<br/>
Максимальное время ожидания в миллисекундах.

### <a name="return-value"></a>Возвращаемое значение

`agent_status` Агента после ожидания завершения. Это может быть `agent_canceled` или `agent_done`.

### <a name="remarks"></a>Примечания

Как задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояний.

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) возникает, если заданного количества времени истечения срока действия, прежде чем агент выполнения задачи.

##  <a name="wait_for_all"></a> wait_for_all

Ожидает, когда все агенты, указанный для выполнения своих задач.

```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Число указателей агента, присутствующих в массиве `_PAgents`.

*_PAgents*<br/>
Массив указателей на агентов для ожидания.

*_PStatus*<br/>
Указатель на массив состояний агента. Значения всех состояний будет представлять состояние соответствующего агента, возвращаемое методом.

*_Timeout*<br/>
Максимальное время ожидания в миллисекундах.

### <a name="remarks"></a>Примечания

Как задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояний.

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) возникает, если заданного количества времени истечения срока действия, прежде чем агент выполнения задачи.

##  <a name="wait_for_one"></a> wait_for_one

Ожидает в течение любого из указанных агентов для выполнения необходимых задач.

```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Число указателей агента, присутствующих в массиве `_PAgents`.

*_PAgents*<br/>
Массив указателей на агентов для ожидания.

*_Status*<br/>
Ссылка на переменную, где будут размещаться состояние агента.

*_Index*<br/>
Ссылка на переменную, которую будет помещен индекс агента.

*_Timeout*<br/>
Максимальное время ожидания в миллисекундах.

### <a name="remarks"></a>Примечания

Как задача агента завершает работу, когда агент вводит `agent_canceled` или `agent_done` состояний.

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) возникает, если заданного количества времени истечения срока действия, прежде чем агент выполнения задачи.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
