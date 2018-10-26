---
title: Класс CNonStatelessWorker | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90c50d3a918f452372aacae5beb36f5425d6a77a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053621"
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

|Имя|Описание|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
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
