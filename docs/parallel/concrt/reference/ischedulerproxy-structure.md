---
title: "Структура ISchedulerProxy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::ISchedulerProxy
dev_langs:
- C++
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: a282e397186ee4ab3eda4f882b9c9fc89ff353f2
ms.lasthandoff: 02/24/2017

---
# <a name="ischedulerproxy-structure"></a>Структура ISchedulerProxy
Интерфейс, по которому планировщики взаимодействуют с диспетчером ресурсов среды выполнения с параллелизмом для согласования выделения ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод ISchedulerProxy::BindContext](#bindcontext)|Связывает с прокси-поток контекста выполнения, если он еще не связан с одним.|  
|[Метод ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Создает новый корень виртуального процессора на аппаратном потоке, связанном с существующим ресурса выполнения.|  
|[Метод ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Запрашивает начального распределения корни виртуального процессора. Каждый корень виртуального процессор представляет возможность выполнения одного потока, который может выполнять работу для планировщика.|  
|[Метод ISchedulerProxy::Shutdown](#shutdown)|Уведомляет диспетчер ресурсов, что планировщик завершает работу. Это вызовет диспетчер ресурсов немедленно освободит все ресурсы, предоставленные планировщику.|  
|[Метод ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Регистрирует текущий поток на диспетчере ресурсов, связывая его с данным планировщиком.|  
|[Метод ISchedulerProxy::UnbindContext](#unbindcontext)|Отсоединяет прокси-поток от контекста выполнения, определяемое `pContext` параметр и возвращает его в свободный пул прокси потоков фабрики. Этот метод может вызываться только на контекст выполнения, который был привязан через [ISchedulerProxy::BindContext](#bindcontext) метод и еще не была запущена через, `pContext` параметр [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) вызова метода.|  
  
## <a name="remarks"></a>Примечания  
 Диспетчер ресурсов передает `ISchedulerProxy` интерфейс для каждого планировщика, которая регистрируется с помощью [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namebindcontexta--ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>Метод ISchedulerProxy::BindContext  
 Связывает с прокси-поток контекста выполнения, если он еще не связан с одним.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pContext`  
 Интерфейс для контекста выполнения для связи с прокси-поток.  
  
### <a name="remarks"></a>Примечания  
 Как правило [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) метод привязывается прокси-поток контекста выполнения по требованию. Есть, однако, случаях, где это необходимо для привязки контекста заранее, чтобы убедиться, что `SwitchTo` метод переключается на уже привязанный контекст. Это случай контекста планирования, как он не может вызвать методы, выделяющие память UMS, а привязка прокси-потока может включать выделения памяти, если прокси-поток не является легко доступным в пуле свободных фабрики прокси-потока.  
  
 `invalid_argument`возникает, если параметр `pContext` имеет значение `NULL`.  
  
##  <a name="a-namecreateoversubscribera--ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>Метод ISchedulerProxy::CreateOversubscriber  
 Создает новый корень виртуального процессора на аппаратном потоке, связанном с существующим ресурса выполнения.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pExecutionResource`  
 `IExecutionResource` Интерфейс, который представляет поток оборудования, необходимо использовать превышение лимита подписки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс `IVirtualProcessorRoot`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, когда ваш планировщик хочет переподписать определенный аппаратный поток в течение ограниченного периода времени. После завершения работы с корневой виртуальный процессор, необходимо вернуть его в диспетчер ресурсов путем вызова [удаление](iexecutionresource-structure.md#remove) метод `IVirtualProcessorRoot` интерфейса.  
  
 Поскольку интерфейс `IVirtualProcessorRoot` наследует от интерфейса `IExecutionResource`, можно даже переподписать существующий корневой виртуальный процессор.  
  
##  <a name="a-namerequestinitialvirtualprocessorsa--ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>Метод ISchedulerProxy::RequestInitialVirtualProcessors  
 Запрашивает начального распределения корни виртуального процессора. Каждый корень виртуального процессор представляет возможность выполнения одного потока, который может выполнять работу для планировщика.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `doSubscribeCurrentThread`  
 Следует ли подписать текущий поток и обеспечивать его во время выделения ресурсов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IExecutionResource` Интерфейса для текущего потока, если параметр `doSubscribeCurrentThread` имеет значение `true`. Если значение равно `false`, метод возвращает `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Перед выполнением планировщиком любой работы, следует использовать этот метод для запроса корней виртуальный процессор из диспетчера ресурсов. Диспетчер ресурсов будет обращаться к политики планировщика с помощью [IScheduler::GetPolicy](ischeduler-structure.md#getpolicy) и использовать значения для ключей политики `MinConcurrency`, `MaxConcurrency` и `TargetOversubscriptionFactor` для определения, сколько аппаратных потоков, присваиваемое планировщик изначально и сколько корни виртуального процессора, чтобы создать для каждого потока оборудования. Дополнительные сведения о том, как политики планировщика используются для определения начального выделения планировщика см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).  
  
 Диспетчер ресурсов предоставляет ресурсы для планировщика, вызвав метод [IScheduler::AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) со списком корни виртуального процессора. Метод вызывается с обратным вызовом в планировщик перед возвратом этот метод.  
  
 Если планировщик запросил подписки для текущего потока, задав для параметра `doSubscribeCurrentThread` для `true`, метод возвращает `IExecutionResource` интерфейса. Подписка должна заканчиваться на более позднем этапе с помощью [IExecutionResource::Remove](iexecutionresource-structure.md#remove) метод.  
  
 При определении, какие аппаратные потоки выбраны, диспетчер ресурсов будет пытаться оптимизации сходства узлов процессора. Если подписка запрашивается для текущего потока, это означает, что текущий поток планирует участвовать в работе, назначенной данному планировщику. В таком случае корней выделенные виртуальных процессоров находятся на узле процессора, которые текущий поток выполняется, если это возможно.  
  
 Процесс подписки потока увеличивает уровень подписки базовой аппаратный поток на единицу. Уровень подписки уменьшается на единицу при завершении подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="a-nameshutdowna--ischedulerproxyshutdown-method"></a><a name="shutdown"></a>Метод ISchedulerProxy::Shutdown  
 Уведомляет диспетчер ресурсов, что планировщик завершает работу. Это вызовет диспетчер ресурсов немедленно освободит все ресурсы, предоставленные планировщику.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Все `IExecutionContext` интерфейсы планировщика, полученные в результате подписка внешний поток, с помощью методов `ISchedulerProxy::RequestInitialVirtualProcessors` или `ISchedulerProxy::SubscribeCurrentThread` должен быть возвращен диспетчеру ресурсов с помощью `IExecutionResource::Remove` перед планировщик завершает свою работу.  
  
 Если у вашего планировщика любой деактивации корни виртуального процессора, необходимо активировать их с помощью [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)и имеют прокси поток, выполнение на них оставить `Dispatch` метод контекстов выполнения, они диспетчеризации, прежде чем вызвать `Shutdown` прокси планировщика.  
  
 Для планировщика необязательно возвращать все корневые виртуальные процессоры, выданные ему диспетчером ресурсов путем вызовов метода `Remove`, поскольку все корневые виртуальные процессоры будут возвращены диспетчеру ресурсов при завершении работы.  
  
##  <a name="a-namesubscribecurrentthreada--ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>Метод ISchedulerProxy::SubscribeCurrentThread  
 Регистрирует текущий поток на диспетчере ресурсов, связывая его с данным планировщиком.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IExecutionResource` Взаимодействия, представляющий текущий поток в среде выполнения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, если требуется, чтобы диспетчер ресурсов с учетом текущего потока, выделяя ресурсы для вашего планировщика и других планировщики. Это особенно полезно, если поток планирует участвовать в работе в очередь планировщика, вместе с корнями виртуальный процессор, которые планировщик получает от диспетчер ресурсов. Диспетчер ресурсов использует сведения для предотвращения ненужной переподписки аппаратных потоков в системе.  
  
 Ресурс выполнения, полученный через этот метод должны быть возвращены для диспетчера ресурсов с помощью [IExecutionResource::Remove](iexecutionresource-structure.md#remove) метод. Поток, который вызывает `Remove` метод должен быть в том же потоке, который ранее вызвал `SubscribeCurrentThread` метод.  
  
 Процесс подписки потока увеличивает уровень подписки базовой аппаратный поток на единицу. Уровень подписки уменьшается на единицу при завершении подписки. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="a-nameunbindcontexta--ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>Метод ISchedulerProxy::UnbindContext  
 Отсоединяет прокси-поток от контекста выполнения, определяемое `pContext` параметр и возвращает его в свободный пул прокси потоков фабрики. Этот метод может вызываться только на контекст выполнения, который был привязан через [ISchedulerProxy::BindContext](#bindcontext) метод и еще не была запущена через, `pContext` параметр [IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto) вызова метода.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pContext`  
 Контекст выполнения, чтобы разорвать связь с его прокси-поток.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IScheduler](ischeduler-structure.md)   
 [Структура IThreadProxy](ithreadproxy-structure.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)   
 [Структура IResourceManager](iresourcemanager-structure.md)

