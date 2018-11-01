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
ms.openlocfilehash: 3d546c7fb11877fbd8cd71d698869ff384b84186
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457758"
---
# <a name="iexecutioncontext-structure"></a>Структура IExecutionContext

Интерфейс для контекста выполнения, который может выполняться на данном виртуальном процессоре и к которому может применяться совместное переключение контекста.

## <a name="syntax"></a>Синтаксис

```
struct IExecutionContext;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IExecutionContext::Dispatch](#dispatch)|Метод, который вызывается, когда прокси-поток запускает выполнение определенного контекста выполнения. Это должна быть основной рабочий процесс для планировщика.|
|[IExecutionContext::GetId](#getid)|Возвращает уникальный идентификатор для контекста выполнения.|
|[IExecutionContext::GetProxy](#getproxy)|Возвращает интерфейс для прокси-поток, который выполняется в этом контексте.|
|[IExecutionContext::GetScheduler](#getscheduler)|Возвращает интерфейс планировщика, к которой принадлежит этот контекст выполнения.|
|[IExecutionContext::SetProxy](#setproxy)|Связывает прокси-поток с данным контекстом выполнения. Связанный прокси-поток вызывает этот метод прямо перед началом выполнения контекста `Dispatch` метод.|

## <a name="remarks"></a>Примечания

Если вы реализуете пользовательский планировщик, который взаимодействует с диспетчером ресурсов среды выполнения с параллелизмом, необходимо реализовать `IExecutionContext` интерфейс. Потоки, создаваемые диспетчером ресурсов выполнять работу от имени вашего планировщика, выполнив `IExecutionContext::Dispatch` метод.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IExecutionContext`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="dispatch"></a>  Метод IExecutionContext::Dispatch

Метод, который вызывается, когда прокси-поток запускает выполнение определенного контекста выполнения. Это должна быть основной рабочий процесс для планировщика.

```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Параметры

*pDispatchState*<br/>
Указатель на состояние, в котором отправляется данного контекста выполнения. Дополнительные сведения о состоянии диспетчеризации, см. в разделе [DispatchState](dispatchstate-structure.md).

##  <a name="getid"></a>  Метод IExecutionContext::GetId

Возвращает уникальный идентификатор для контекста выполнения.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный целочисленный идентификатор.

### <a name="remarks"></a>Примечания

Следует использовать метод `GetExecutionContextId` получить уникальный идентификатор для объекта, который реализует `IExecutionContext` диспетчером ресурсов предоставленный интерфейс, прежде чем использовать в качестве параметра методов интерфейса. Вы должны возвращать тот же идентификатор при `GetId` функция вызывается.

Идентификатор, полученный из разных источников может привести к неопределенному поведению.

##  <a name="getproxy"></a>  Метод IExecutionContext::GetProxy

Возвращает интерфейс для прокси-поток, который выполняется в этом контексте.

```
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IThreadProxy`. Если контекст выполнения прокси-поток не был инициализирован с помощью вызова `SetProxy`, эта функция должна возвратить `NULL`.

### <a name="remarks"></a>Примечания

Диспетчер ресурсов будет вызывать `SetProxy` метод на контекст выполнения с `IThreadProxy` интерфейсом в виде параметра, прежде чем входить `Dispatch` метод в контексте. Ожидается, что пользователь для хранения этого аргумента и вернуть его при вызовах метода `GetProxy()`.

##  <a name="getscheduler"></a>  Метод IExecutionContext::GetScheduler

Возвращает интерфейс планировщика, к которой принадлежит этот контекст выполнения.

```
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IScheduler`.

### <a name="remarks"></a>Примечания

Необходимо инициализировать контекст выполнения с допустимым `IScheduler` интерфейс, прежде чем использовать его в качестве параметра для методов, предоставленные диспетчером ресурсов.

##  <a name="setproxy"></a>  Метод IExecutionContext::SetProxy

Связывает прокси-поток с данным контекстом выполнения. Связанный прокси-поток вызывает этот метод прямо перед началом выполнения контекста `Dispatch` метод.

```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Параметры

*pThreadProxy*<br/>
Интерфейс для прокси-поток, который собираетесь введите `Dispatch` метод в данном контексте выполнения.

### <a name="remarks"></a>Примечания

Вы должны сохранить параметр `pThreadProxy` и возвратить его во время вызова `GetProxy` метод. Диспетчер ресурсов гарантирует, что прокси-поток, связанный с контекстом выполнения остаются неизменными во время выполнения прокси-поток `Dispatch` метод.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)
