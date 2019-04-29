---
title: Структура IExecutionResource
ms.date: 11/04/2016
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
ms.openlocfilehash: 9f8f5c5629e9794ca8ee2cc6bedbc4ba6bfdb24d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262519"
---
# <a name="iexecutionresource-structure"></a>Структура IExecutionResource

Абстракция для аппаратного потока.

## <a name="syntax"></a>Синтаксис

```
struct IExecutionResource;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|Возвращает число активированных виртуальный процессор корней, подписка на внешних угроз, связанных с базовой аппаратный поток, который представляет этот ресурс выполнения.|
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.|
|[IExecutionResource::GetNodeId](#getnodeid)|Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.|
|[IExecutionResource::Remove](#remove)|Возвращает диспетчеру ресурсов для данного ресурса выполнения.|

## <a name="remarks"></a>Примечания

Вычислительные ресурсы могут быть автономными или связанные с корни виртуального процессора. Автономный ресурс выполнения создается в том случае, когда поток в приложении создает подписку потока. Методы [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) и [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) создать подписки потоков и вернуть `IExecutionResource` интерфейс, представляющий подписка. Создание подписки потока — это способ информирования диспетчера ресурсов, который данного потока будет участвовать в работе в очереди планировщика, вместе с Resource Manager назначает планировщику корни виртуального процессора. Диспетчер ресурсов использует сведения во избежание переподписки аппаратных потоков, где это возможно.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IExecutionResource`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="currentsubscriptionlevel"></a>  Метод IExecutionResource::CurrentSubscriptionLevel

Возвращает число активированных виртуальный процессор корней, подписка на внешних угроз, связанных с базовой аппаратный поток, который представляет этот ресурс выполнения.

```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий уровень подписки.

### <a name="remarks"></a>Примечания

Уровень подписки сообщает, сколько выполняющиеся потоки связаны с потоком оборудования. Это включает только потоки, которые диспетчер ресурсов учитывает в форме подписанных потоков и корни виртуального процессора, которые активно выполняют прокси-потоки.

Вызов метода [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), или метод [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) с параметром `doSubscribeCurrentThread` присвоено значение **true** увеличивает уровень подписки на аппаратный поток на единицу. Они также возвращают `IExecutionResource` интерфейс, представляющий подписку. Соответствующего вызова [IExecutionResource::Remove](#remove) уменьшает уровень подписки аппаратный поток на единицу.

Процесс активации с помощью метода корневом виртуальном процессоре [IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate) увеличивает уровень подписки на аппаратный поток на единицу. Методы [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), или [IExecutionResource::Remove](#remove) уменьшение на единицу при вызове для корневого виртуального процессора, активированные уровня подписки.

Диспетчер ресурсов использует сведения уровня подписки, как один из способов определить, когда нужно перемещать ресурсы между планировщиками.

##  <a name="getexecutionresourceid"></a>  Метод IExecutionResource::GetExecutionResourceId

Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.

```
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для аппаратного потока, базового данного ресурса выполнения.

### <a name="remarks"></a>Примечания

Каждый аппаратный поток назначается уникальный идентификатор среды выполнения с параллелизмом. Если соответствующее оборудование находятся несколько ресурсов выполнения потока, они будут иметь один и тот же идентификатор ресурса выполнения.

##  <a name="getnodeid"></a>  Метод IExecutionResource::GetNodeId

Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.

```
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для узла процессора.

### <a name="remarks"></a>Примечания

Среда выполнения с параллелизмом представляет аппаратных потоков в системе в группах узлов процессора. Узлы обычно являются производными от топологии оборудования системы. Например все процессоры на определенном сокете или определенный узел NUMA могут входить в одном узле процессора. Диспетчер ресурсов назначает уникальные идентификаторы для этих узлов, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее количество узлов процессора в системе.

Количество узлов может быть получен из функции [GetProcessorNodeCount](concurrency-namespace-functions.md).

##  <a name="remove"></a>  Метод IExecutionResource::Remove

Возвращает диспетчеру ресурсов для данного ресурса выполнения.

```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>Параметры

*pScheduler*<br/>
Интерфейс планировщика, выполняющего запрос для удаления данного ресурса выполнения.

### <a name="remarks"></a>Примечания

Используйте этот метод для возврата автономных ресурсов выполнения, а также выполнения ресурсы, связанные с корни виртуального процессора для диспетчера ресурсов.

Если это автономный ресурс выполнения, полученный от любого из методов [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) или [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), вызов функции метод `Remove` будет завершен поток подписку, ресурс был создан для представления. Требуется завершить все подписки потока перед завершением работы планировщика прокси-сервер и необходимо вызвать `Remove` из потока, создавшего подписку.

Корни виртуального процессора также могут быть возвращены диспетчеру ресурсов путем вызова метода `Remove`, поскольку интерфейс `IVirtualProcessorRoot` наследуется от интерфейса `IExecutionResource`. Может потребоваться возвращать корневой виртуальный процессор, либо в ответ на вызов [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) метод, или когда вы закончите с корнем переподписан виртуального процессора, полученный от [ ISchedulerProxy::CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) метод. Корни виртуального процессора, нет никаких ограничений на каком потоке может вызывать `Remove` метод.

`invalid_argument` возникает, если параметр `pScheduler` присваивается `NULL`.

`invalid_operation` возникает, если параметр `pScheduler` отличается от планировщика, что этот ресурс выполнения был создан, или, к автономный ресурс выполнения, если текущий поток отличается от потока, который создал подписку потока.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)
