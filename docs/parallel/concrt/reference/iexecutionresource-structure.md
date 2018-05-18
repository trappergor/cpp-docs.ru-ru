---
title: Структура IExecutionResource | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc69c30f30d25179427ee8e59c536bb7cb5b483d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="iexecutionresource-structure"></a>Структура IExecutionResource
Абстракция для аппаратного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|Возвращает число активированных виртуального процессора корней и подписанные внешние потоки, которые в текущий момент связан с базовой аппаратный поток, который представляет этот ресурс выполнения.|  
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.|  
|[IExecutionResource::GetNodeId](#getnodeid)|Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.|  
|[IExecutionResource::Remove](#remove)|Возвращает диспетчер ресурсов для данного ресурса выполнения.|  
  
## <a name="remarks"></a>Примечания  
 Вычислительные ресурсы могут быть автономными или связанные с корни виртуального процессора. Автономный ресурс выполнения создается, когда поток в приложении создает подписку потока. Методы [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) и [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) создания подписки потоков и возврата `IExecutionResource` интерфейс, представляющий подписка. Создание подписки потока является способом информирования диспетчер ресурсов, что заданный поток будет участвовать в работе, помещенных в очередь планировщика, а также назначает диспетчером ресурсов планировщику корни виртуального процессора. Диспетчер ресурсов использует сведения для избежать переподписки аппаратных потоков, где это возможно.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IExecutionResource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="currentsubscriptionlevel"></a>  Метод IExecutionResource::CurrentSubscriptionLevel  
 Возвращает число активированных виртуального процессора корней и подписанные внешние потоки, которые в текущий момент связан с базовой аппаратный поток, который представляет этот ресурс выполнения.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий уровень подписки.  
  
### <a name="remarks"></a>Примечания  
 Уровень подписки сообщает, сколько выполняющиеся потоки связаны с потоком оборудования. Это включает только потоки, которые диспетчер ресурсов учитывает в форме подписанных потоков и корни виртуального процессора, которые активно выполняют прокси-потоки.  
  
 Вызов метода [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), или метод [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) с параметром `doSubscribeCurrentThread` присвоено значение `true`увеличивает на единицу уровня подписки аппаратного потока. Они также возвращают `IExecutionResource` интерфейс, представляющий подписку. С соответствующим вызовом [IExecutionResource::Remove](#remove) уменьшает уровень подписки аппаратного потока на единицу.  
  
 Процесс активации корневой виртуальный процессор, с помощью метода [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate) увеличивает на единицу уровня подписки аппаратного потока. Методы [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), или [IExecutionResource::Remove](#remove) уменьшения уровня подписки на единицу при вызове в корневом элементе активированной виртуального процессора.  
  
 Диспетчер ресурсов использует сведения уровня подписки как один из способов определить, когда нужно переместить ресурсы между планировщиками.  
  
##  <a name="getexecutionresourceid"></a>  Метод IExecutionResource::GetExecutionResourceId  
 Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор для аппаратного потока, базового данного ресурса выполнения.  
  
### <a name="remarks"></a>Примечания  
 Каждый поток оборудования присваивается уникальный идентификатор среды выполнения с параллелизмом. Если несколько ресурсов выполнения, соответствующее оборудование потока, они будут иметь один и тот же идентификатор ресурса выполнения.  
  
##  <a name="getnodeid"></a>  Метод IExecutionResource::GetNodeId  
 Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор для узла процессора.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения с параллелизмом предоставляет аппаратных потоков в группах узлов процессора в системе. Узлы обычно являются производными от топологии оборудования системы. Например все процессоры на определенном сокете или определенном узле NUMA могут входить в одном узле процессора. Диспетчер ресурсов присваивает уникальные идентификаторы для этих узлов, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее число узлов процессора в системе.  
  
 Количество узлов, которые могут быть получены из функции [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="remove"></a>  Метод IExecutionResource::Remove  
 Возвращает диспетчер ресурсов для данного ресурса выполнения.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pScheduler`  
 Интерфейс планировщика, выполняющего запрос, чтобы удалить этот ресурс выполнения.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для возврата автономных ресурсов выполнения, а также ресурсов выполнения, связанных с корни виртуального процессора для диспетчера ресурсов.  
  
 Если это автономный ресурс выполнения, полученный от любого из методов [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) или [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), вызов метод `Remove` завершается подписки потока, который ресурс был создан для представления. Требуется завершить всех подписки потоков перед завершением работы прокси планировщика и необходимо вызвать метод `Remove` из потока, создавшего подписку.  
  
 Корни виртуального процессора также могут быть возвращены диспетчеру ресурсов путем вызова метода `Remove`, поскольку интерфейс `IVirtualProcessorRoot` наследуется от интерфейса `IExecutionResource`. Может потребоваться вернуть корневой виртуальный процессор, или в ответ на вызов [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) метод, или когда вы закончите корень переподписан виртуального процессора, полученный от [ ISchedulerProxy::CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) метод. Корни виртуального процессора, нет никаких ограничений в каком потоке может вызывать `Remove` метод.  
  
 `invalid_argument` вызывается, если параметр `pScheduler` равно `NULL`.  
  
 `invalid_operation` вызывается, если параметр `pScheduler` отличается от планировщика, что этот ресурс выполнения был создан для или с автономным ресурсом выполнения, если текущий поток отличается от потока, который создал подписку потока.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)
