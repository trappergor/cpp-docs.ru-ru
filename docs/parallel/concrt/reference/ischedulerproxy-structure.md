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
ms.openlocfilehash: f4a9e79c2da56406610ad6da08fb438e2f92923d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368163"
---
# <a name="ischedulerproxy-structure"></a>Структура ISchedulerProxy

Интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов среды выполнения с параллелизмом для согласования выделения ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
struct ISchedulerProxy;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ISchedulerProxy::BindContext](#bindcontext)|Связывает контекст выполнения с прокси-сервером потока, если он еще не связан с ним.|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Создает новый укор в виртуальном процессоре на аппаратном потоке, связанном с существующим ресурсом выполнения.|
|[ISchedulerProxy::ЗапросПервоначальныеВиртуальныеПроцессоры](#requestinitialvirtualprocessors)|Запрашивает первоначальное распределение корней виртуального процессора. Каждый универс апервый виртуальный процессор представляет собой возможность выполнения одного потока, который может выполнять работу для планировщика.|
|[ISchedulerПрокси::Закрытие](#shutdown)|Уведомляет менеджера ресурсов о закрытии планировщика. Это приведет к тому, что менеджер ресурсов немедленно вернет все ресурсы, предоставленные планировщику.|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Регистрирует текущий поток с диспетчером ресурсов, связывая его с этим планировщиком.|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|Отсажает прокси-сервер потока из `pContext` контекста выполнения, указанного параметром, и возвращает его в свободный пул прокси-сервера. Этот метод может быть вызван только на контексте выполнения, который был связан через метод [ISchedulerProxy](#bindcontext) и еще не был запущен через `pContext` параметр вызова [метода IThreadProxy::SwitchTo.](ithreadproxy-structure.md#switchto)|

## <a name="remarks"></a>Remarks

Менеджер ресурсов вручает `ISchedulerProxy` интерфейс каждому планировщику, который регистрируется с ним с помощью метода [IResourceManager::RegisterScheduler.](iresourcemanager-structure.md#registerscheduler)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ISchedulerProxy`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>ISchedulerProxy::Метод BindContext

Связывает контекст выполнения с прокси-сервером потока, если он еще не связан с ним.

```cpp
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Интерфейс контекста выполнения для ассоциации с прокси-сервером потока.

### <a name="remarks"></a>Remarks

Как правило, метод [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) связывает прокси-сервер потока с контекстом выполнения по требованию. Однако существуют обстоятельства, при которых необходимо заранее связать `SwitchTo` контекст, с тем чтобы обеспечить переход метода в уже связанный контекст. Это относится к контексту планирования UMS, так как он не может вызвать методы, выделяющие память, и связывание прокси потока может включать выделение памяти, если прокси потока не легко доступен в свободном пуле фабрики прокси потока.

`invalid_argument`брошен, если `pContext` параметр `NULL`имеет значение.

## <a name="ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>ISchedulerProxy::Метод создателя

Создает новый укор в виртуальном процессоре на аппаратном потоке, связанном с существующим ресурсом выполнения.

```cpp
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Параметры

*pExecutionResource*<br/>
Интерфейс, `IExecutionResource` представляющий аппаратный поток, который необходимо переподписать.

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IVirtualProcessorRoot`.

### <a name="remarks"></a>Remarks

Используйте этот метод, когда планировщик хочет переподписаться на определенный аппаратный поток в течение ограниченного периода времени. После того, как вы закончите с корнем виртуального процессора, вы `IVirtualProcessorRoot` должны вернуть его менеджеру ресурсов, позвонив [методу Удалить](iexecutionresource-structure.md#remove) на интерфейсе.

Поскольку интерфейс `IVirtualProcessorRoot` наследует от интерфейса `IExecutionResource`, можно даже переподписать существующий корневой виртуальный процессор.

## <a name="ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>ISchedulerProxy::ЗапросПервоначальныйВиртуальныйМетод

Запрашивает первоначальное распределение корней виртуального процессора. Каждый универс апервый виртуальный процессор представляет собой возможность выполнения одного потока, который может выполнять работу для планировщика.

```cpp
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Параметры

*doSubscribeCurrentThread*<br/>
Подписаться на текущий поток и учесть его при распределении ресурсов.

### <a name="return-value"></a>Возвращаемое значение

Интерфейс `IExecutionResource` для текущего потока, `doSubscribeCurrentThread` если параметр имеет значение **верно.** Если значение **ложное,** метод возвращает NULL.

### <a name="remarks"></a>Remarks

Прежде чем планировщик выполняет любую работу, он должен использовать этот метод, чтобы запросить корни виртуального процессора у менеджера ресурсов. Менеджер ресурсов получит доступ к политике планировщика с помощью [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) `MinConcurrency`и `MaxConcurrency` `TargetOversubscriptionFactor` будет использовать значения для ключей политики, а также определить, сколько аппаратных потоков назначить планировщику изначально и сколько виртуальных корней процессора для создания для каждого аппаратного потока. Для получения дополнительной информации о том, как политики планировщика используются для определения первоначального распределения планировщика, [см. PolicyElementKey.](concurrency-namespace-enums.md)

Менеджер ресурсов предоставляет ресурсы планировщику, позвонив по методу [IScheduler::AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) со списком корней виртуальных процессоров. Метод вызывается в качестве обратного вызова в планировщик перед возвращением этого метода.

Если планировщик запросил подписку для текущего `doSubscribeCurrentThread` потока, установив параметр `IExecutionResource` на **истину,** метод возвращает интерфейс. Подписка должна быть прекращена в более поздней точке с помощью метода [IExecutionResource::Remove.](iexecutionresource-structure.md#remove)

При определении того, какие аппаратные потоки выбраны, диспетчер ресурсов попытается оптимизировать сродство узла процессора. Если запрашивается подписка для текущего потока, это означает, что текущий поток намеревается участвовать в работе, назначенной этому планировщику. В таком случае выделенные корни виртуальных процессоров расположены на узло процессора, на который, по возможности, выполняется текущий поток.

Акт подписки на поток увеличивает уровень подписки базового аппаратного потока на один. Уровень подписки снижается на один, когда подписка прекращается. Для получения дополнительной информации об уровнях подписки см. [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyshutdown-method"></a><a name="shutdown"></a>ISchedulerProxy::Метод выключения

Уведомляет менеджера ресурсов о закрытии планировщика. Это приведет к тому, что менеджер ресурсов немедленно вернет все ресурсы, предоставленные планировщику.

```cpp
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Remarks

Все `IExecutionContext` интерфейсы, полученные планировщиком в результате подписки на внешний `ISchedulerProxy::SubscribeCurrentThread` поток с помощью `IExecutionResource::Remove` методов, `ISchedulerProxy::RequestInitialVirtualProcessors` или должны быть возвращены диспетчеру ресурсов, используя его до того, как планировщик выключится.

Если у планировщика были какие-либо отключенные корни виртуального процессора, вы должны активировать их с помощью [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate), и иметь прокси-серверы потока, исполняющие на них, оставить `Dispatch` метод контекстов выполнения, которые они отправляют, прежде чем вызвать `Shutdown` на прокси-сервере планировщика.

Для планировщика необязательно возвращать все корневые виртуальные процессоры, выданные ему диспетчером ресурсов путем вызовов метода `Remove`, поскольку все корневые виртуальные процессоры будут возвращены диспетчеру ресурсов при завершении работы.

## <a name="ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>ISchedulerProxy::SubscribeCurrentThread Метод

Регистрирует текущий поток с диспетчером ресурсов, связывая его с этим планировщиком.

```cpp
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Взаимодействие, `IExecutionResource` представляющее текущий поток во времени выполнения.

### <a name="remarks"></a>Remarks

Используйте этот метод, если вы хотите, чтобы менеджер ресурсов отчитывался за текущий поток при распределении ресурсов для планировщика и других планировщиков. Это особенно полезно, когда поток планирует участвовать в работе в очереди к планировщику, наряду с корнями виртуального процессора, которые планировщик получает от менеджера ресурсов. Диспетчер ресурсов использует информацию для предотвращения ненужной переподписки аппаратных потоков в системе.

Ресурс выполнения, полученный с помощью этого метода, должен быть возвращен диспетчеру ресурсов с помощью [метода IExecutionResource::Remove.](iexecutionresource-structure.md#remove) Поток, который `Remove` вызывает метод, должен быть тем `SubscribeCurrentThread` же потоком, который ранее назывался методом.

Акт подписки на поток увеличивает уровень подписки базового аппаратного потока на один. Уровень подписки снижается на один, когда подписка прекращается. Для получения дополнительной информации об уровнях подписки см. [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>ISchedulerProxy::UnbindContext Метод

Отсажает прокси-сервер потока из `pContext` контекста выполнения, указанного параметром, и возвращает его в свободный пул прокси-сервера. Этот метод может быть вызван только на контексте выполнения, который был связан через метод [ISchedulerProxy](#bindcontext) и еще не был запущен через `pContext` параметр вызова [метода IThreadProxy::SwitchTo.](ithreadproxy-structure.md#switchto)

```cpp
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Параметры

*pContext*<br/>
Контекст выполнения, чтобы отмежеваться от прокси потока.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IScheduler](ischeduler-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
