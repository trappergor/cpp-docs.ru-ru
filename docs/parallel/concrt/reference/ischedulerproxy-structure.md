---
title: Структура ISchedulerProxy | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
dev_langs:
- C++
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65198998666391763ef32a55cd12e86529e619ed
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693927"
---
# <a name="ischedulerproxy-structure"></a>Структура ISchedulerProxy
Интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов среды выполнения с параллелизмом для согласования выделения ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ISchedulerProxy::BindContext](#bindcontext)|Связывает с прокси-поток контекста выполнения, если он еще не связан с одним.|  
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Создает новый корневой виртуальный процессор для аппаратного потока, связанного с существующим ресурса выполнения.|  
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Запрашивает начального распределения корни виртуального процессора. Каждый корень виртуального процессора представляет возможность выполнения одного потока, который может выполнять работу для планировщика.|  
|[ISchedulerProxy::Shutdown](#shutdown)|Уведомляет диспетчер ресурсов, что планировщик завершает работу. Это приведет к диспетчеру ресурсов немедленно освободит все ресурсы, предоставленные планировщику.|  
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Регистрирует текущий поток на диспетчере ресурсов, связывая его с данным планировщиком.|  
|[ISchedulerProxy::UnbindContext](#unbindcontext)|Отсоединяет прокси-поток от контекста выполнения, определяемое `pContext` параметр и возвращает его в пул свободной фабрики прокси-потока. Этот метод может вызываться только на контекст выполнения, который был привязан через [ISchedulerProxy::BindContext](#bindcontext) метод и еще не была запущена через, `pContext` параметр [IThreadProxy::SwitchTo ](ithreadproxy-structure.md#switchto) вызова метода.|  
  
## <a name="remarks"></a>Примечания  
 Передает диспетчер ресурсов `ISchedulerProxy` интерфейс для каждого планировщика, который регистрирует его с помощью [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="bindcontext"></a>  Метод ISchedulerProxy::BindContext  
 Связывает с прокси-поток контекста выполнения, если он еще не связан с одним.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pContext`  
 Интерфейс для контекста выполнения для связи с прокси-поток.  
  
### <a name="remarks"></a>Примечания  
 Как правило [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) метод привязывается прокси-поток контекста выполнения по требованию. Существуют, однако обстоятельства, где это необходимо для привязки контекста заранее, чтобы убедиться, что `SwitchTo` метод переключается на уже привязанный контекст. Это случай контекста планирования, как он не может вызывать методы, которые выделения памяти UMS, а привязка прокси-потока может включать выделения памяти, если прокси-поток не доступны в пуле свободных фабрики прокси-потока.  
  
 `invalid_argument` вызывается, если параметр `pContext` имеет значение `NULL`.  
  
##  <a name="createoversubscriber"></a>  Метод ISchedulerProxy::CreateOversubscriber  
 Создает новый корневой виртуальный процессор для аппаратного потока, связанного с существующим ресурса выполнения.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pExecutionResource`  
 `IExecutionResource` Интерфейс, который представляет аппаратного потока, необходимо использовать превышение лимита подписки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс `IVirtualProcessorRoot`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, если ваш планировщик хочет переподписать определенный аппаратный поток на ограниченное время. После завершения работы с корневой виртуальный процессор, необходимо вернуть его в диспетчер ресурсов путем вызова [удалить](iexecutionresource-structure.md#remove) метод `IVirtualProcessorRoot` интерфейса.  
  
 Поскольку интерфейс `IVirtualProcessorRoot` наследует от интерфейса `IExecutionResource`, можно даже переподписать существующий корневой виртуальный процессор.  
  
##  <a name="requestinitialvirtualprocessors"></a>  Метод ISchedulerProxy::RequestInitialVirtualProcessors  
 Запрашивает начального распределения корни виртуального процессора. Каждый корень виртуального процессора представляет возможность выполнения одного потока, который может выполнять работу для планировщика.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `doSubscribeCurrentThread`  
 Следует ли подписать текущий поток и обеспечивать его во время выделения ресурсов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IExecutionResource` Интерфейса для текущего потока, если параметр `doSubscribeCurrentThread` имеет значение `true`. Если значение равно `false`, метод возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Перед выполнением планировщиком какой-либо работы, его следует использовать этот метод для запроса корней виртуальный процессор из диспетчера ресурсов. Диспетчер ресурсов затронет политики планировщика с помощью [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) и использовать значения для ключей политики `MinConcurrency`, `MaxConcurrency` и `TargetOversubscriptionFactor` для определения количества потоков оборудования для назначения Планировщик изначально и сколько корни виртуального процессора, чтобы создать для каждого потока оборудования. Дополнительные сведения о том, как политики планировщика используются для определения начального выделения см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).  
  
 Диспетчер ресурсов предоставляет ресурсов планировщику путем вызова метода [IScheduler::AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) со списком корни виртуального процессора. Метод вызывается как обратный вызов в планировщик перед возвратом этот метод.  
  
 Если планировщик запрошена подписки для текущего потока, установив параметр `doSubscribeCurrentThread` для `true`, метод возвращает `IExecutionResource` интерфейса. Подписка должна заканчиваться на более позднем этапе с помощью [IExecutionResource::Remove](iexecutionresource-structure.md#remove) метод.  
  
 При определении, какие аппаратные потоки выбраны, диспетчер ресурсов будет пытаться оптимизации сходства узлов процессора. Если подписка запрашивается для текущего потока, это означает, что текущий поток планирует участвовать в работу, назначенную данным планировщиком. В таком случае корней выделенные виртуальных процессоров находятся на узле процессора, которые текущий поток выполняется, если это возможно.  
  
 Процесс подписки потока увеличивает уровень подписки базовой аппаратный поток на единицу. Уровень подписки уменьшается на единицу при завершении подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="shutdown"></a>  Метод ISchedulerProxy::Shutdown  
 Уведомляет диспетчер ресурсов, что планировщик завершает работу. Это приведет к диспетчеру ресурсов немедленно освободит все ресурсы, предоставленные планировщику.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Все `IExecutionContext` интерфейсы планировщика, полученные в результате подписка внешний поток, с помощью методов `ISchedulerProxy::RequestInitialVirtualProcessors` или `ISchedulerProxy::SubscribeCurrentThread` должны быть возвращены для диспетчера ресурсов с помощью `IExecutionResource::Remove` перед планировщик завершает свою работу.  
  
 Если бы планировщика любой деактивации корни виртуального процессора, необходимо активировать их с помощью [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)и иметь поток прокси-серверы, выполняемые на их оставить `Dispatch` метод выполнения они диспетчеризации, прежде чем вызвать контексты `Shutdown` прокси планировщика.  
  
 Для планировщика необязательно возвращать все корневые виртуальные процессоры, выданные ему диспетчером ресурсов путем вызовов метода `Remove`, поскольку все корневые виртуальные процессоры будут возвращены диспетчеру ресурсов при завершении работы.  
  
##  <a name="subscribecurrentthread"></a>  Метод ISchedulerProxy::SubscribeCurrentThread  
 Регистрирует текущий поток на диспетчере ресурсов, связывая его с данным планировщиком.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IExecutionResource` Взаимодействие, представляющий текущий поток в среде выполнения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, если требуется, чтобы диспетчер ресурсов для учетной записи для текущего потока при выделении ресурсов к данным планировщиком и другими планировщиками. Это особенно полезно в тех случаях, когда поток планирует участвовать в работе в очередь планировщика, вместе с корни виртуального процессора, которые планировщик получает из диспетчера ресурсов. Диспетчер ресурсов использует сведения для предотвращения ненужной переподписки аппаратных потоков в системе.  
  
 Ресурс выполнения, получаемые с помощью этого метода должны быть возвращены для диспетчера ресурсов с помощью [IExecutionResource::Remove](iexecutionresource-structure.md#remove) метод. Поток, который вызывает `Remove` метод должен быть в том же потоке, который ранее вызвал `SubscribeCurrentThread` метод.  
  
 Процесс подписки потока увеличивает уровень подписки базовой аппаратный поток на единицу. Уровень подписки уменьшается на единицу при завершении подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="unbindcontext"></a>  Метод ISchedulerProxy::UnbindContext  
 Отсоединяет прокси-поток от контекста выполнения, определяемое `pContext` параметр и возвращает его в пул свободной фабрики прокси-потока. Этот метод может вызываться только на контекст выполнения, который был привязан через [ISchedulerProxy::BindContext](#bindcontext) метод и еще не была запущена через, `pContext` параметр [IThreadProxy::SwitchTo ](ithreadproxy-structure.md#switchto) вызова метода.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pContext`  
 Контекст выполнения для отмены связи с его прокси-поток.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IScheduler](ischeduler-structure.md)   
 [Структура IThreadProxy](ithreadproxy-structure.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)   
 [Структура IResourceManager](iresourcemanager-structure.md)
