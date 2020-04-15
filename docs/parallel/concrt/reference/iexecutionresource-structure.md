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
ms.openlocfilehash: 4305948aa4e5da36023c1d4fe8b0b84aa4d59e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377319"
---
# <a name="iexecutionresource-structure"></a>Структура IExecutionResource

Абстракция для аппаратного потока.

## <a name="syntax"></a>Синтаксис

```cpp
struct IExecutionResource;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IExecutionРесурс::ТекущийУровень подписки](#currentsubscriptionlevel)|Возвращает количество активированных корней виртуального процессора и подписанных внешних потоков, в настоящее время связанных с базовым аппаратным потоком, который представляет ресурс выполнения.|
|[IExecutionРесурс:::Газета.Наука](#getexecutionresourceid)|Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.|
|[IExecutionРесурс:::GetNodeId](#getnodeid)|Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс исполнения.|
|[IExecutionРесурс::Удалить](#remove)|Возвращает этот ресурс выполнения менеджеру ресурсов.|

## <a name="remarks"></a>Remarks

Ресурсы выполнения могут быть автономными или ассоциироваться с корнями виртуального процессора. Ресурс автономного выполнения создается, когда поток в приложении создает подписку потока. Методы [ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) и [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) создают подписку `IExecutionResource` на потоки и возвращают интерфейс, представляющий подписку. Создание подписки на поток — это способ информирования менеджера ресурсов о том, что данный поток будет участвовать в работе, встающей в очередь к планировщику, а также виртуальному процессору, который менеджер ресурсов присваивает планировщику. Диспетчер ресурсов использует эту информацию, чтобы избежать переподписки аппаратных потоков там, где это возможно.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IExecutionResource`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="iexecutionresourcecurrentsubscriptionlevel-method"></a><a name="currentsubscriptionlevel"></a>IExecutionResource::Текущий метод подписки

Возвращает количество активированных корней виртуального процессора и подписанных внешних потоков, в настоящее время связанных с базовым аппаратным потоком, который представляет ресурс выполнения.

```cpp
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий уровень подписки.

### <a name="remarks"></a>Remarks

Уровень подписки показывает, сколько ходовых потоков связано с аппаратным потоком. Это включает только потоки, о которым и знает менеджер ресурсов в виде подписных потоков, и корни виртуальных процессоров, которые активно исполняют прокси-потоки.

Вызов метода [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), или метод [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) с параметром, `doSubscribeCurrentThread` установленным к значению **истинных** приращений уровня подписки аппаратного потока по одному. Они также `IExecutionResource` возвращают интерфейс, представляющий подписку. Соответствующий вызов [iExecutionResource::Удаление](#remove) декретов уровня подписки аппаратного потока на один.

Акт активации корня виртуального процессора с помощью метода [IVirtualProcessorRoot::Активировать](ivirtualprocessorroot-structure.md#activate) уровень подписки аппаратного потока по одному. Методы [IVirtualProcessorRoot::Deactivate](ivirtualprocessorroot-structure.md#deactivate), или [IExecutionResource::Удалить](#remove) decrement уровень подписки по одному при вызове на активированный корень виртуального процессора.

Менеджер ресурсов использует информацию об уровне подписки как один из способов определения того, когда перемещать ресурсы между планировщиками.

## <a name="iexecutionresourcegetexecutionresourceid-method"></a><a name="getexecutionresourceid"></a>IExecutionРесурс::GetExecutionResourceId Метод

Возвращает уникальный идентификатор для аппаратного потока, который представляет этот ресурс выполнения.

```cpp
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для аппаратного потока, лежащего в основе этого ресурса выполнения.

### <a name="remarks"></a>Remarks

Каждый аппаратный поток присваивается уникальным идентификатором в concurrency Runtime. Если несколько ресурсов выполнения связаны с аппаратным потоком, все они будут иметь один и тот же идентификатор ресурсов выполнения.

## <a name="iexecutionresourcegetnodeid-method"></a><a name="getnodeid"></a>IExecutionResource::GetNodeId Метод

Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс исполнения.

```cpp
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для узла процессора.

### <a name="remarks"></a>Remarks

Concurrency Runtime представляет аппаратные потоки в системе в группах узлов процессоров. Узлы обычно получаются из аппаратной топологии системы. Например, все процессоры на определенном гнезде или определенном узлах NUMA могут принадлежать к одному и тому же узлам процессора. Диспетчер ресурсов присваивает эти узлы `0` уникальным идентификаторам, начиная с до и включая, `nodeCount - 1`где `nodeCount` представлено общее количество узлов процессора в системе.

Количество узлов можно получить из функции [GetProcessorNodeCount.](concurrency-namespace-functions.md)

## <a name="iexecutionresourceremove-method"></a><a name="remove"></a>IExecutionРесурс::Удалить метод

Возвращает этот ресурс выполнения менеджеру ресурсов.

```cpp
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>Параметры

*pПланировщик*<br/>
Интерфейс для планировщика, делающего запрос на удаление этого ресурса выполнения.

### <a name="remarks"></a>Remarks

Используйте этот метод для возврата ресурсов автономного выполнения, а также ресурсов выполнения, связанных с корнями виртуального процессора, в ресурсный диспетчер.

Если это автономный ресурс выполнения, который вы получили от любого из методов [ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) или [ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), вызов метода `Remove` завершит подписку потока, которую ресурс был создан для представления. Вы должны закончить все подписки потока до закрытия прокси-сервера планировщика, и должны вызвать `Remove` из потока, который создал подписку.

Корни виртуального процессора также могут быть возвращены диспетчеру ресурсов путем вызова метода `Remove`, поскольку интерфейс `IVirtualProcessorRoot` наследуется от интерфейса `IExecutionResource`. Возможно, вам придется вернуть корень виртуального процессора либо в ответ на звонок в [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) метод, или когда вы сделали с переподписанным виртуальный процессор корень вы получили от [ISchedulerProxy::CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) метод. Для корней виртуального процессора нет никаких ограничений, на которых поток может вызвать `Remove` метод.

`invalid_argument`брошен, если `pScheduler` параметр `NULL`установлен на.

`invalid_operation`брошен, если `pScheduler` параметр отличается от планировщика, для которого был создан этот ресурс выполнения, или с автономным ресурсом выполнения, если текущий поток отличается от потока, создавого подписку на поток.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)
