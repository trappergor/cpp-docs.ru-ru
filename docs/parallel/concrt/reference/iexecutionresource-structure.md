---
title: "Структура IExecutionResource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 16
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: fa3c65780ac9e001e6f6b8a015dc7f70df47181f
ms.lasthandoff: 03/17/2017

---
# <a name="iexecutionresource-structure"></a>Структура IExecutionResource
Абстракция для аппаратного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|Возвращает число активированных виртуальный процессор корней и подписанные внешние потоки, в данный момент связанный с базовой аппаратный поток, который представляет этот ресурс выполнения.|  
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.|  
|[IExecutionResource::GetNodeId](#getnodeid)|Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.|  
|[IExecutionResource::Remove](#remove)|Возвращает этот ресурс выполнения диспетчеру ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 Ресурсы выполнения могут быть автономными или связанные с корни виртуального процессора. Автономный ресурс выполнения создается, когда поток в приложении создает подписку потока. Методы [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) и [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) создания подписки потоков и возврата `IExecutionResource` интерфейс, представляющий подписку. Создание подписки потока является способом информирования диспетчер ресурсов, что данный поток будет участвовать в работе в очереди планировщика, а также корни виртуального процессора, назначает диспетчером ресурсов планировщику. Диспетчер ресурсов использует сведения для избежать переподписки аппаратных потоков, где его можно.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IExecutionResource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="currentsubscriptionlevel"></a>Метод IExecutionResource::CurrentSubscriptionLevel  
 Возвращает число активированных виртуальный процессор корней и подписанные внешние потоки, в данный момент связанный с базовой аппаратный поток, который представляет этот ресурс выполнения.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущий уровень подписки.  
  
### <a name="remarks"></a>Примечания  
 Уровень подписки сообщает, сколько выполняющиеся потоков связаны с потоком оборудования. Это включает только потоки, которые диспетчер ресурсов учитывает в форме подписанных потоков и корни виртуального процессора, которые активно выполняют прокси-потоки.  
  
 Вызов метода [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), или метод [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) с параметром `doSubscribeCurrentThread` задано значение `true` увеличивает уровень подписки на аппаратный поток на единицу. Они также возвращают `IExecutionResource` интерфейс, представляющий подписку. Соответствующий вызов [IExecutionResource::Remove](#remove) уменьшает уровень подписки на аппаратный поток на единицу.  
  
 Процесс активации корня виртуального процессора, с помощью метода [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate) увеличивает уровень подписки на аппаратный поток на единицу. Методы [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), или [IExecutionResource::Remove](#remove) уменьшения уровня подписки на единицу при вызове для корневого каталога активации виртуальный процессор.  
  
 Диспетчер ресурсов использует сведения уровня подписки как один из способов определить, когда нужно переместить ресурсы между планировщиками.  
  
##  <a name="getexecutionresourceid"></a>Метод IExecutionResource::GetExecutionResourceId  
 Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор для аппаратного потока основан данный ресурс выполнения.  
  
### <a name="remarks"></a>Примечания  
 Каждому аппаратному потоку присваивается уникальный идентификатор средой выполнения с параллелизмом. Если несколько ресурсов выполнения, соответствующее оборудование потока, они будут иметь один и тот же идентификатор ресурса выполнения.  
  
##  <a name="getnodeid"></a>Метод IExecutionResource::GetNodeId  
 Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор для узла процессора.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения с параллелизмом предоставляет аппаратных потоков в группах узлов процессора в системе. Узлы обычно являются производными от топологии оборудования системы. Например все процессоры на определенном сокете или определенном узле NUMA могут принадлежать к одному узлу процессора. Диспетчер ресурсов присваивает уникальные идентификаторы этих узлов, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее число узлов процессора в системе.  
  
 Количество узлов, которые могут быть получены из функции [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="remove"></a>Метод IExecutionResource::Remove  
 Возвращает этот ресурс выполнения диспетчеру ресурсов.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pScheduler`  
 Интерфейс к планировщик, посылающий запрос, чтобы удалить этот ресурс выполнения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для возврата автономных ресурсов выполнения, а также ресурсов выполнения, связанных с корни виртуального процессора для диспетчера ресурсов.  
  
 Если это автономный ресурс выполнения, полученный от любой из методов [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) или [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), вызов метода `Remove` закончится подписки потока, созданного ресурса для представления. Требуется завершить всех подписки потоков перед завершением работы прокси планировщика, а также необходимо вызвать `Remove` из потока, который создал подписку.  
  
 Корни виртуального процессора также могут быть возвращены диспетчеру ресурсов путем вызова метода `Remove`, поскольку интерфейс `IVirtualProcessorRoot` наследуется от интерфейса `IExecutionResource`. Необходимо возвращать корневой виртуальный процессор, либо в ответ на вызов [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) метода или завершении корневой виртуальный процессор, переподписан, получен из [ISchedulerProxy::CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) метод. Корни виртуального процессора, нет никаких ограничений на каком потоке может вызывать `Remove` метод.  
  
 `invalid_argument`возникает, если параметр `pScheduler` равен `NULL`.  
  
 `invalid_operation`возникает, если параметр `pScheduler` отличается от планировщика, что этот ресурс выполнения был создан или, с автономным ресурсом выполнения, если текущий поток отличается от потока, который создал подписку потока.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)

