---
title: Структура ISchedulerProxy
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: 0dddd43a5b3e68992e41f0b95893303e57e7c7ff
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268854"
---
# <a name="ischedulerproxy-structure"></a>Структура ISchedulerProxy

Интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов среды выполнения с параллелизмом для согласования выделения ресурсов.

## <a name="syntax"></a>Синтаксис

```
struct ISchedulerProxy;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[ISchedulerProxy::BindContext](#bindcontext)|Связывает контекст выполнения с прокси-поток, если он еще не связан с одним.|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Создает новый корневой виртуальный процессор на аппаратный поток, связанный с существующим ресурса выполнения.|
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Запрашивает начального распределения корни виртуального процессора. Каждый корневой виртуальный процессор представляет возможность выполнения одного потока, который может выполнять работу для планировщика.|
|[ISchedulerProxy::Shutdown](#shutdown)|Уведомляет диспетчер ресурсов о том, что планировщик завершает работу. Это приведет к Resource Manager, чтобы немедленно освободить все ресурсы, предоставленные планировщику.|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Регистрирует текущего потока с диспетчером ресурсов, сопоставляя его с данным планировщиком.|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|Отменяет связь прокси-поток из контекста выполнения, определяемое `pContext` параметр и возвращает его в пул бесплатных фабрики прокси-потока. Этот метод может вызываться только на контекст выполнения, который был привязан через [ISchedulerProxy::BindContext](#bindcontext) метод еще не были запущены через, `pContext` параметр [IThreadProxy::SwitchTo ](ithreadproxy-structure.md#switchto) вызов метода.|

## <a name="remarks"></a>Примечания

Передает диспетчер ресурсов `ISchedulerProxy` интерфейс для каждого планировщика, которая регистрируется с помощью [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) метод.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISchedulerProxy`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="bindcontext"></a>  Метод ISchedulerProxy::BindContext

Связывает контекст выполнения с прокси-поток, если он еще не связан с одним.

```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Интерфейс для контекста выполнения для связи с прокси-поток.

### <a name="remarks"></a>Примечания

Как правило [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) метод привязывается прокси-поток контекста выполнения по требованию. Существуют, однако обстоятельства, где это необходимо для привязки контекста заранее, чтобы убедиться, что `SwitchTo` метод переключается на уже привязанных контекст. Это происходит планирования контекста, так как он не может вызвать методы, выделяющие память UMS и привязки прокси-поток может включать выделения памяти, если прокси-поток отсутствует в пуле свободных фабрики прокси-потока.

`invalid_argument` возникает, если параметр `pContext` имеет значение `NULL`.

##  <a name="createoversubscriber"></a>  Метод ISchedulerProxy::CreateOversubscriber

Создает новый корневой виртуальный процессор на аппаратный поток, связанный с существующим ресурса выполнения.

```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Параметры

*pExecutionResource*<br/>
`IExecutionResource` Интерфейс, который представляет аппаратный поток, нужно превысить предел подписок.

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IVirtualProcessorRoot`.

### <a name="remarks"></a>Примечания

Этот метод следует используйте, когда планировщик хочет превысить предел подписок определенного аппаратного потока в течение ограниченного времени. Закончив с корневого виртуального процессора, нужно вернуть в диспетчер ресурсов путем вызова [удалить](iexecutionresource-structure.md#remove) метод `IVirtualProcessorRoot` интерфейс.

Поскольку интерфейс `IVirtualProcessorRoot` наследует от интерфейса `IExecutionResource`, можно даже переподписать существующий корневой виртуальный процессор.

##  <a name="requestinitialvirtualprocessors"></a>  Метод ISchedulerProxy::RequestInitialVirtualProcessors

Запрашивает начального распределения корни виртуального процессора. Каждый корневой виртуальный процессор представляет возможность выполнения одного потока, который может выполнять работу для планировщика.

```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Параметры

*doSubscribeCurrentThread*<br/>
Следует ли подписаться текущий поток и обеспечивать его во время выделения ресурсов.

### <a name="return-value"></a>Возвращаемое значение

`IExecutionResource` Интерфейс для текущего потока, если параметр `doSubscribeCurrentThread` имеет значение **true**. Если значение равно **false**, метод возвращает значение NULL.

### <a name="remarks"></a>Примечания

Перед выполнением планировщиком какой-либо работы, его следует использовать этот метод для запроса корни виртуального процессора из Resource Manager. Диспетчер ресурсов будет доступ к политики планировщика с помощью [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) и используйте значения для ключей политики `MinConcurrency`, `MaxConcurrency` и `TargetOversubscriptionFactor` чтобы определить, сколько аппаратных потоков, чтобы назначить Планировщик изначально и сколько корни виртуального процессора, чтобы создать для каждого аппаратного потока. Дополнительные сведения о том, как политики планировщика используются для определения начального выделения, см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).

Диспетчер ресурсов предоставляет ресурсы для планировщика путем вызова метода [IScheduler::AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) со списком корни виртуального процессора. Метод вызывается как обратный вызов в планировщик, перед возвратом этот метод.

Если планировщик запросили подписку для текущего потока, присвоив параметру `doSubscribeCurrentThread` для **true**, метод возвращает `IExecutionResource` интерфейс. Подписки должны завершаться в дальнейшем с помощью [IExecutionResource::Remove](iexecutionresource-structure.md#remove) метод.

При определении, какие аппаратные потоки выбраны, диспетчер ресурсов будет пытаться оптимизировать для процессора сходство узлов. Если подписка запрашивается для текущего потока, это означает, что текущий поток планирует участвовать в работе, назначенные данным планировщиком. В таком случае корни выделенных виртуальных процессоров, находятся в узле процессора, которые текущий поток выполняется, если это возможно.

Процесс подписки потока увеличивает уровень подписки базовой аппаратный поток на единицу. Уровень подписки уменьшается на единицу при завершении подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="shutdown"></a>  Метод ISchedulerProxy::Shutdown

Уведомляет диспетчер ресурсов о том, что планировщик завершает работу. Это приведет к Resource Manager, чтобы немедленно освободить все ресурсы, предоставленные планировщику.

```
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Примечания

Все `IExecutionContext` интерфейсы планировщика, получаемые в результате подписка внешний поток, с помощью методов `ISchedulerProxy::RequestInitialVirtualProcessors` или `ISchedulerProxy::SubscribeCurrentThread` должен возвращаться для диспетчера ресурсов с помощью `IExecutionResource::Remove` прежде, чем планировщик завершает свою работу.

Если у вас планировщик любой деактивации корни виртуального процессора, необходимо активировать их с помощью [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)и поток прокси-серверы на их оставить `Dispatch` метод выполнения контексты, они диспетчеризации перед вызовом `Shutdown` на учетную запись-посредник для планировщика.

Для планировщика необязательно возвращать все корневые виртуальные процессоры, выданные ему диспетчером ресурсов путем вызовов метода `Remove`, поскольку все корневые виртуальные процессоры будут возвращены диспетчеру ресурсов при завершении работы.

##  <a name="subscribecurrentthread"></a>  Метод ISchedulerProxy::SubscribeCurrentThread

Регистрирует текущего потока с диспетчером ресурсов, сопоставляя его с данным планировщиком.

```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

`IExecutionResource` Взаимодействии, представляющий текущий поток в среде выполнения.

### <a name="remarks"></a>Примечания

Этот метод следует используйте, если требуется, чтобы диспетчер ресурсов для учетной записи для текущего потока при выделении ресурсов для вашего планировщика и другие планировщики. Это особенно полезно в тех случаях, когда поток планирует участвовать в работе в очередь планировщика, вместе с корни виртуального процессора, которые планировщик получает из Resource Manager. Диспетчер ресурсов использует сведения, чтобы предотвратить ненужные превышение лимита подписки аппаратных потоков в системе.

Ресурс выполнения, полученный с помощью этого метода должны быть возвращены диспетчеру ресурсов с помощью [IExecutionResource::Remove](iexecutionresource-structure.md#remove) метод. Поток, вызывающий `Remove` метод должен быть в том же потоке, который ранее вызвал `SubscribeCurrentThread` метод.

Процесс подписки потока увеличивает уровень подписки базовой аппаратный поток на единицу. Уровень подписки уменьшается на единицу при завершении подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="unbindcontext"></a>  Метод ISchedulerProxy::UnbindContext

Отменяет связь прокси-поток из контекста выполнения, определяемое `pContext` параметр и возвращает его в пул бесплатных фабрики прокси-потока. Этот метод может вызываться только на контекст выполнения, который был привязан через [ISchedulerProxy::BindContext](#bindcontext) метод еще не были запущены через, `pContext` параметр [IThreadProxy::SwitchTo ](ithreadproxy-structure.md#switchto) вызов метода.

```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Контекст выполнения для отмены связи с его прокси-поток.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
