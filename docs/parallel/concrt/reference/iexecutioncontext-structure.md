---
title: Структура IExecutionContext
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 45d65a5e16121d39233c3ceb801933aa1f5a5f8e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138914"
---
# <a name="iexecutioncontext-structure"></a>Структура IExecutionContext

Интерфейс для контекста выполнения, который может выполняться на данном виртуальном процессоре и к которому может применяться совместное переключение контекста.

## <a name="syntax"></a>Синтаксис

```cpp
struct IExecutionContext;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[IExecutionContext::D Patch](#dispatch)|Метод, вызываемый, когда прокси-поток запускает выполнение определенного контекста выполнения. Это должна быть Основная рабочая подпрограммы для планировщика.|
|[IExecutionContext:: GetId](#getid)|Возвращает уникальный идентификатор контекста выполнения.|
|[IExecutionContext::-proxy](#getproxy)|Возвращает интерфейс прокси-сервера потока, который исполняет этот контекст.|
|[IExecutionContext:: "Scheduler"](#getscheduler)|Возвращает интерфейс к планировщику, которому принадлежит контекст выполнения.|
|[IExecutionContext:: Сетпрокси](#setproxy)|Связывает прокси-поток с этим контекстом выполнения. Связанный прокси-поток вызывает этот метод прямо перед выполнением метода `Dispatch` контекста.|

## <a name="remarks"></a>Remarks

При реализации пользовательского планировщика, который взаимодействует с диспетчер ресурсовом среда выполнения с параллелизмом, необходимо реализовать интерфейс `IExecutionContext`. Потоки, созданные диспетчер ресурсов, выполняют работу от имени планировщика, выполняя метод `IExecutionContext::Dispatch`.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IExecutionContext`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="dispatch"></a>IExecutionContext::D метода Patch

Метод, вызываемый, когда прокси-поток запускает выполнение определенного контекста выполнения. Это должна быть Основная рабочая подпрограммы для планировщика.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Параметры

*пдиспатчстате*<br/>
Указатель на состояние, под которым отправляется этот контекст выполнения. Дополнительные сведения о состоянии диспетчеризации см. в разделе [DispatchState](dispatchstate-structure.md).

## <a name="getid"></a>Метод IExecutionContext:: GetId

Возвращает уникальный идентификатор контекста выполнения.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный целочисленный идентификатор.

### <a name="remarks"></a>Remarks

Для получения уникального идентификатора объекта, реализующего интерфейс `IExecutionContext`, следует использовать метод `GetExecutionContextId`, прежде чем использовать интерфейс в качестве параметра для методов, предоставляемых диспетчер ресурсов. При вызове функции `GetId` должен возвращаться тот же идентификатор.

Идентификатор, полученный из другого источника, может привести к неопределенному поведению.

## <a name="getproxy"></a>Метод IExecutionContext::-proxy

Возвращает интерфейс прокси-сервера потока, который исполняет этот контекст.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IThreadProxy`. Если прокси-сервер потока контекста выполнения не был инициализирован с помощью вызова `SetProxy`, функция должна возвращать `NULL`.

### <a name="remarks"></a>Remarks

Диспетчер ресурсов вызовет метод `SetProxy` в контексте выполнения с интерфейсом `IThreadProxy` в качестве параметра перед входом в метод `Dispatch` в контексте. Предполагается, что этот аргумент сохраняется и возвращается в вызовах `GetProxy()`.

## <a name="getscheduler"></a>Метод IExecutionContext:: Scheduler

Возвращает интерфейс к планировщику, которому принадлежит контекст выполнения.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IScheduler`.

### <a name="remarks"></a>Remarks

Необходимо инициализировать контекст выполнения с допустимым интерфейсом `IScheduler`, прежде чем использовать его в качестве параметра для методов, предоставляемых диспетчер ресурсов.

## <a name="setproxy"></a>Метод IExecutionContext:: Сетпрокси

Связывает прокси-поток с этим контекстом выполнения. Связанный прокси-поток вызывает этот метод прямо перед выполнением метода `Dispatch` контекста.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Параметры

*псреадпрокси*<br/>
Интерфейс для прокси-сервера потока, который собирается ввести метод `Dispatch` в этом контексте выполнения.

### <a name="remarks"></a>Remarks

Предполагается, что параметр сохраняется `pThreadProxy` и возвращается при вызове метода `GetProxy`. Диспетчер ресурсов гарантирует, что прокси-сервер потока, связанный с контекстом выполнения, не изменится во время выполнения прокси-сервером потока метода `Dispatch`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)
