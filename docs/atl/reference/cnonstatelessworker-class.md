---
title: Класс CNonStatelessWorker
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: abfd3e585c843fcc4ed4ad273c8ed217eaaccb7d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245534"
---
# <a name="cnonstatelessworker-class"></a>Класс CNonStatelessWorker

Получает запросы из пула потоков и передают их в рабочий объект, который создается и уничтожается при каждом запросе.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Параметры

*Рабочей роли*<br/>
Класс рабочего потока, удовлетворяющие [рабочий архетип](../../atl/reference/worker-archetype.md) подходит для обработки запросов в очереди на [CThreadPool](../../atl/reference/cthreadpool-class.md).

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CNonStatelessWorker::Execute](#execute)|Реализация [WorkerArchetype::Execute](worker-archetype.md#execute).|
|[CNonStatelessWorker::Initialize](#initialize)|Реализация [WorkerArchetype::Initialize](worker-archetype.md#initialize).|
|[CNonStatelessWorker::Terminate](#terminate)|Реализация [WorkerArchetype::Terminate](worker-archetype.md#terminate).|

## <a name="remarks"></a>Примечания

Этот класс является простой рабочий поток для использования с [CThreadPool](../../atl/reference/cthreadpool-class.md). Этот класс не предоставляет все возможности обработки запросов, свои собственные. Вместо этого он создает один экземпляр *рабочих* каждого запроса и делегирует реализацию его методов к этому экземпляру.

Преимущество этого класса заключается в обеспечении удобный способ изменения состояния модели для существующих классов рабочих потоков. `CThreadPool` будет создан один сотрудник в течение времени существования потока, поэтому если рабочий класс содержит состояние, она будет содержать несколько запросов. Просто поместить этот класс в `CNonStatelessWorker` шаблона перед его с использованием `CThreadPool`, время существования рабочую роль и состояние, он содержит только один запрос.

## <a name="requirements"></a>Требования

**Заголовок:** файлов atlutil.h

##  <a name="execute"></a>  CNonStatelessWorker::Execute

Реализация [WorkerArchetype::Execute](worker-archetype.md#execute).

```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Примечания

Этот метод создает экземпляр класса *рабочих* класс на стек и вызывает [инициализировать](worker-archetype.md#initialize) на этот объект. Если инициализация прошла успешно, этот метод также вызывает [Execute](worker-archetype.md#execute) и [Terminate](worker-archetype.md#terminate) того же объекта.

##  <a name="initialize"></a>  CNonStatelessWorker::Initialize

Реализация [WorkerArchetype::Initialize](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Возвращаемое значение

Всегда возвращает значение TRUE.

### <a name="remarks"></a>Примечания

Этот класс не выполняет инициализацию `Initialize`.

##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType

Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Примечания

Этот класс обрабатывает же тип рабочего элемента, как класс, используемый для *рабочих* параметр шаблона. См. в разделе [CNonStatelessWorker Обзор](../../atl/reference/cnonstatelessworker-class.md) подробные сведения.

##  <a name="terminate"></a>  CNonStatelessWorker::Terminate

Реализация [WorkerArchetype::Terminate](worker-archetype.md#terminate).

```
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Примечания

Этот класс не выполняет очистку `Terminate`.

## <a name="see-also"></a>См. также

[Класс CThreadPool](../../atl/reference/cthreadpool-class.md)<br/>
[Рабочий архетип](../../atl/reference/worker-archetype.md)<br/>
[Классы](../../atl/reference/atl-classes.md)
