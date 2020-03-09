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
ms.openlocfilehash: f0092f5f90bbdf253c09dbdc80849c3db472212f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78882942"
---
# <a name="agent-class"></a>Класс agent

Класс, предназначенный для использования в качестве базового класса для всех независимых агентов. Он используется для скрытия состояния от других агентов и взаимодействия посредством передачи сообщений.

## <a name="syntax"></a>Синтаксис

```cpp
class agent;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Субагент](#ctor)|Перегружен. Конструирует агент.|
|[Деструктор агента ~](#dtor)|Уничтожает агент.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[cancel](#cancel)|Перемещает агент из состояния `agent_created` или `agent_runnable` в состояние `agent_canceled`.|
|[start](#start)|Перемещает агент из состояния `agent_created` в состояние `agent_runnable` и планирует его выполнение.|
|[status](#status)|Синхронный источник сведений о состоянии от агента.|
|[status_port](#status_port)|Асинхронный источник сведений о состоянии от агента.|
|[ожидания](#wait)|Ожидает завершения задачи агента.|
|[wait_for_all](#wait_for_all)|Ожидает завершения задач всеми указанными агентами.|
|[wait_for_one](#wait_for_one)|Ожидает завершения задачи одним из указанных агентов.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Description|
|----------|-----------------|
|[Договорились](#done)|Перемещает агент в состояние `agent_done`, указывая на то, что агент завершен.|
|[run](#run)|Представляет главную задачу агента. `run` должен быть переопределен в производном классе и указывает, что должен делать агент после его запуска.|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [асинхронные агенты](../../../parallel/concrt/asynchronous-agents.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`agent`

## <a name="requirements"></a>Требования

**Заголовок:** agents.h

**Пространство имен:** concurrency

## <a name="ctor"></a>Субагент

Конструирует агент.

```cpp
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```

### <a name="parameters"></a>Параметры

*_PScheduler*<br/>
Объект `Scheduler`, в рамках которого запланирована задача выполнения агента.

*_PGroup*<br/>
Объект `ScheduleGroup`, в рамках которого запланирована задача выполнения агента. Используемый объект `Scheduler` подразумевается группой расписаний.

### <a name="remarks"></a>Remarks

Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PGroup` .

## <a name="dtor"></a>~ агент

Уничтожает агент.

```cpp
virtual ~agent();
```

### <a name="remarks"></a>Remarks

Удаление агента, который не находится в состоянии терминала (`agent_done` или `agent_canceled`), является ошибкой. Это можно избежать, ожидая, когда агент достигнет состояния терминала в деструкторе класса, наследуемого от класса `agent`.

## <a name="cancel"></a>Отмена

Перемещает агент из состояния `agent_created` или `agent_runnable` в состояние `agent_canceled`.

```cpp
bool cancel();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если агент был отменен; в противном случае — **значение false** . Агент не может быть отменен, если он уже запущен или уже завершен.

## <a name="done"></a>Договорились

Перемещает агент в состояние `agent_done`, указывая на то, что агент завершен.

```cpp
bool done();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если агент перемещен в состояние `agent_done`; в противном случае — **значение false** . Отмененный агент нельзя переместить в состояние `agent_done`.

### <a name="remarks"></a>Remarks

Этот метод должен вызываться в конце метода `run`, если известно, что выполнение агента завершено.

## <a name="run"></a>запуска

Представляет главную задачу агента. `run` должен быть переопределен в производном классе и указывает, что должен делать агент после его запуска.

```cpp
virtual void run() = 0;
```

### <a name="remarks"></a>Remarks

Перед вызовом этого метода состояние агента изменяется на `agent_started` вправо. Метод должен вызвать `done` агента с соответствующим состоянием перед возвратом и не может вызывать исключения.

## <a name="start"></a>запустить

Перемещает агент из состояния `agent_created` в состояние `agent_runnable` и планирует его выполнение.

```cpp
bool start();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если агент запущен правильно; в противном случае — **значение false** . Не удается запустить агент, который был отменен.

## <a name="status"></a>состояние

Синхронный источник сведений о состоянии от агента.

```cpp
agent_status status();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текущее состояние агента. Обратите внимание, что возвращаемое состояние может измениться сразу после возврата.

## <a name="status_port"></a>status_port

Асинхронный источник сведений о состоянии от агента.

```cpp
ISource<agent_status>* status_port();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает источник сообщения, который может отправить сообщения о текущем состоянии агента.

## <a name="wait"></a>ожидания

Ожидает завершения задачи агента.

```cpp
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*_PAgent*<br/>
Указатель на агент, который нужно ожидать.

*_Timeout*<br/>
Максимальное время ожидания (в миллисекундах).

### <a name="return-value"></a>Возвращаемое значение

`agent_status` агента по завершении ожидания. Это может быть либо `agent_canceled`, либо `agent_done`.

### <a name="remarks"></a>Remarks

Задача агента завершается, когда агент переходит в состояние `agent_canceled` или `agent_done`.

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если срок действия указанного времени истекает до того, как агент завершит свою задачу.

## <a name="wait_for_all"></a>wait_for_all

Ожидает завершения задач всеми указанными агентами.

```cpp
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Число указателей агентов, имеющихся в `_PAgents`массива.

*_PAgents*<br/>
Массив указателей на агенты, которые нужно ожидать.

*_PStatus*<br/>
Указатель на массив состояний агента. Каждое значение состояния будет представлять состояние соответствующего агента при возврате из метода.

*_Timeout*<br/>
Максимальное время ожидания (в миллисекундах).

### <a name="remarks"></a>Remarks

Задача агента завершается, когда агент переходит в состояние `agent_canceled` или `agent_done`.

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если срок действия указанного времени истекает до того, как агент завершит свою задачу.

## <a name="wait_for_one"></a>wait_for_one

Ожидает завершения задачи одним из указанных агентов.

```cpp
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Число указателей агентов, имеющихся в `_PAgents`массива.

*_PAgents*<br/>
Массив указателей на агенты, которые нужно ожидать.

*_Status*<br/>
Ссылка на переменную, в которой будет размещено состояние агента.

*_Index*<br/>
Ссылка на переменную, в которую будет помещен индекс агента.

*_Timeout*<br/>
Максимальное время ожидания (в миллисекундах).

### <a name="remarks"></a>Remarks

Задача агента завершается, когда агент переходит в состояние `agent_canceled` или `agent_done`.

Если параметр `_Timeout` имеет значение, отличное от константы `COOPERATIVE_TIMEOUT_INFINITE`, исключение [operation_timed_out](operation-timed-out-class.md) создается, если срок действия указанного времени истекает до того, как агент завершит свою задачу.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
