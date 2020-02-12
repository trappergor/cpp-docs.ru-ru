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
ms.openlocfilehash: 40799d1ed6e21e6932f1adfbad117c436918b792
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141275"
---
# <a name="iexecutionresource-structure"></a>Структура IExecutionResource

Абстракция для аппаратного потока.

## <a name="syntax"></a>Синтаксис

```cpp
struct IExecutionResource;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[IExecutionResource:: Куррентсубскриптионлевел](#currentsubscriptionlevel)|Возвращает число активированных корней виртуальных процессоров и подписанных внешних потоков, которые в настоящее время связаны с базовым аппаратным потоком, который представляет этот ресурс выполнения.|
|[IExecutionResource:: Жетексекутионресаурцеид](#getexecutionresourceid)|Возвращает уникальный идентификатор аппаратного потока, представляемого этим ресурсом выполнения.|
|[IExecutionResource:: GetNodeId](#getnodeid)|Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.|
|[IExecutionResource:: Remove](#remove)|Возвращает этот ресурс выполнения в диспетчер ресурсов.|

## <a name="remarks"></a>Remarks

Ресурсы выполнения могут быть автономными или связанными с корнями виртуальных процессоров. Автономный ресурс выполнения создается, когда поток в приложении создает подписку потока. Методы [ISchedulerProxy:: субскрибесреад](ischedulerproxy-structure.md#subscribecurrentthread) и [ISchedulerProxy:: рекуестинитиалвиртуалпроцессорс](ischedulerproxy-structure.md#requestinitialvirtualprocessors) создают подписки потоков и возвращают интерфейс `IExecutionResource`, представляющий подписку. Создание подписки на поток — это способ информирования диспетчер ресурсов о том, что данный поток будет участвовать в очереди работ, поставленной в очередь планировщика, вместе с корнями виртуального процессора, диспетчер ресурсов назначены планировщику. Диспетчер ресурсов использует эти сведения, чтобы избежать переподписки аппаратных потоков, где это возможно.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IExecutionResource`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="currentsubscriptionlevel"></a>Метод IExecutionResource:: Куррентсубскриптионлевел

Возвращает число активированных корней виртуальных процессоров и подписанных внешних потоков, которые в настоящее время связаны с базовым аппаратным потоком, который представляет этот ресурс выполнения.

```cpp
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Текущий уровень подписки.

### <a name="remarks"></a>Remarks

Уровень подписки сообщает, сколько работающих потоков связано с аппаратным потоком. Сюда относятся только потоки, на которые диспетчер ресурсов осведомлены в виде подписанных потоков, а также корни виртуального процессора, которые активно выполняют прокси-серверы потоков.

Вызов метода [ISchedulerProxy:: субскрибекуррентсреад](ischedulerproxy-structure.md#subscribecurrentthread)или метода [ISchedulerProxy:: рекуестинитиалвиртуалпроцессорс](ischedulerproxy-structure.md#requestinitialvirtualprocessors) с параметром, `doSubscribeCurrentThread` значение **true** , увеличивает уровень подписки аппаратного потока на единицу. Они также возвращают интерфейс `IExecutionResource`, представляющий подписку. Соответствующий вызов метода [IExecutionResource:: Remove](#remove) уменьшает уровень подписки аппаратного потока на единицу.

Процесс активации корня виртуального процессора с помощью метода [ивиртуалпроцессоррут:: Activate](ivirtualprocessorroot-structure.md#activate) увеличивает уровень подписки аппаратного потока на единицу. Методы [ивиртуалпроцессоррут::D еактивате](ivirtualprocessorroot-structure.md#deactivate)или [IExecutionResource:: Remove](#remove) уменьшают уровень подписки на один при вызове на активированном корне виртуального процессора.

Диспетчер ресурсов использует сведения уровня подписки в качестве одного из способов определения момента перемещения ресурсов между планировщиками.

## <a name="getexecutionresourceid"></a>Метод IExecutionResource:: Жетексекутионресаурцеид

Возвращает уникальный идентификатор аппаратного потока, представляемого этим ресурсом выполнения.

```cpp
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор аппаратного потока, лежащего в основе этого ресурса выполнения.

### <a name="remarks"></a>Remarks

Каждому аппаратному потоку назначается уникальный идентификатор среда выполнения с параллелизмом. Если несколько ресурсов выполнения связаны с аппаратным потоком, все они будут иметь одинаковый идентификатор ресурса выполнения.

## <a name="getnodeid"></a>Метод IExecutionResource:: GetNodeId

Возвращает уникальный идентификатор для узла процессора, к которому принадлежит этот ресурс выполнения.

```cpp
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор для узла процессора.

### <a name="remarks"></a>Remarks

Среда выполнения с параллелизмом представляет аппаратные потоки в системе в группах узлов процессора. Узлы обычно являются производными от топологии оборудования системы. Например, все процессоры на определенном сокете или определенном узле NUMA могут принадлежать одному и тому же узлу процессора. Диспетчер ресурсов назначает уникальные идентификаторы этим узлам, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее число узлов процессора в системе.

Количество узлов можно получить из функции [жетпроцессорнодекаунт](concurrency-namespace-functions.md).

## <a name="remove"></a>Метод IExecutionResource:: Remove

Возвращает этот ресурс выполнения в диспетчер ресурсов.

```cpp
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>Параметры

*псчедулер*<br/>
Интерфейс планировщика, который делает запрос на удаление этого ресурса выполнения.

### <a name="remarks"></a>Remarks

Используйте этот метод для возврата ресурсов автономного выполнения, а также ресурсов выполнения, связанных с корнями виртуального процессора, в диспетчер ресурсов.

Если это автономный ресурс выполнения, полученный из любого из методов [ISchedulerProxy:: субскрибекуррентсреад](ischedulerproxy-structure.md#subscribecurrentthread) или [ISchedulerProxy:: рекуестинитиалвиртуалпроцессорс](ischedulerproxy-structure.md#requestinitialvirtualprocessors), вызов метода `Remove` приведет к завершению подписки потока, которую будет представлять ресурс. Перед завершением работы прокси планировщика необходимо завершить все подписки потоков, а также вызвать `Remove` из потока, создавшего подписку.

Корни виртуального процессора также могут быть возвращены диспетчеру ресурсов путем вызова метода `Remove`, поскольку интерфейс `IVirtualProcessorRoot` наследуется от интерфейса `IExecutionResource`. Может потребоваться возврат корня виртуального процессора либо в ответ на вызов метода [IScheduler:: ремовевиртуалпроцессорс](ischeduler-structure.md#removevirtualprocessors) , либо при завершении с помощью переподписанного корня виртуального процессора, полученного из метода [ISchedulerProxy:: креатеоверсубскрибер](ischedulerproxy-structure.md#createoversubscriber) . Для корней виртуального процессора нет ограничений на то, какой поток может вызвать метод `Remove`.

`invalid_argument` возникает, если параметр `pScheduler` имеет значение `NULL`.

`invalid_operation` возникает, если параметр `pScheduler` отличается от планировщика, для которого был создан этот ресурс выполнения, или, с автономным ресурсом выполнения, если текущий поток отличается от потока, создавшего подписку потока.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)
