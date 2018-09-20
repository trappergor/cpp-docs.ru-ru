---
title: Структура IScheduler | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c926589165cbf93bd517612514bc27c88f28e15
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378869"
---
# <a name="ischeduler-structure"></a>Структура IScheduler

Интерфейс для абстракции планировщика работы. Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками работы.

## <a name="syntax"></a>Синтаксис

```
struct IScheduler;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|Предоставляет планировщик с набором корни виртуального процессора для его использования. Каждый `IVirtualProcessorRoot` интерфейс представляет право на выполнение одного потока, который может выполнять работу от имени планировщик.|
|[IScheduler::GetId](#getid)|Возвращает уникальный идентификатор для планировщика.|
|[IScheduler::GetPolicy](#getpolicy)|Возвращает копию объекта политики планировщика. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).|
|[IScheduler::NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Уведомляет этот планировщик, аппаратных потоков, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другие планировщики.|
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Уведомляет этот планировщик, аппаратных потоков, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другие планировщики.|
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|Инициирует удаление корни виртуального процессора, которые ранее были выделены данного планировщика.|
|[IScheduler::Statistics](#statistics)|Предоставляет сведения, относящиеся к скорость прибытия и завершения задач и изменение длины очереди для планировщика.|

## <a name="remarks"></a>Примечания

Если при реализации пользовательских планировщика, который взаимодействует с диспетчером ресурсов, необходимо предоставить реализацию `IScheduler` интерфейс. Этот интерфейс — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов. Другой конец представленного `IResourceManager` и `ISchedulerProxy` интерфейсы, используемые диспетчером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IScheduler`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="addvirtualprocessors"></a>  Метод IScheduler::AddVirtualProcessors

Предоставляет планировщик с набором корни виртуального процессора для его использования. Каждый `IVirtualProcessorRoot` интерфейс представляет право на выполнение одного потока, который может выполнять работу от имени планировщик.

```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Параметры

*ppVirtualProcessorRoots*<br/>
Массив `IVirtualProcessorRoot` интерфейсы, представляющий виртуальный процессор корней, добавляемого к планировщику.

*count*<br/>
Количество `IVirtualProcessorRoot` интерфейсов в массиве.

### <a name="remarks"></a>Примечания

Диспетчер ресурсов вызывает `AddVirtualProcessor` метод для предоставления первоначального набора корней виртуальный процессор планировщику. Он также может вызывать этот метод для добавления корни виртуального процессора на планировщик при перебалансировке ресурсов между планировщиками.

##  <a name="getid"></a>  Метод IScheduler::GetId

Возвращает уникальный идентификатор для планировщика.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный целочисленный идентификатор.

### <a name="remarks"></a>Примечания

Следует использовать [GetSchedulerId](concurrency-namespace-functions.md) функцию для получения уникального идентификатора для объекта, который реализует `IScheduler` диспетчером ресурсов предоставленный интерфейс, прежде чем использовать в качестве параметра методов интерфейса. Вы должны возвращать тот же идентификатор при `GetId` функция вызывается.

Идентификатор, полученный из разных источников может привести к неопределенному поведению.

##  <a name="getpolicy"></a>  Метод IScheduler::GetPolicy

Возвращает копию объекта политики планировщика. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Копия политики планировщика.

##  <a name="notifyresourcesexternallybusy"></a>  Метод IScheduler::NotifyResourcesExternallyBusy

Уведомляет этот планировщик, аппаратных потоков, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другие планировщики.

```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Параметры

*ppVirtualProcessorRoots*<br/>
Массив `IVirtualProcessorRoot` интерфейсов, связанных с аппаратных потоков, на которых другие планировщики стали занят.

*count*<br/>
Количество `IVirtualProcessorRoot` интерфейсов в массиве.

### <a name="remarks"></a>Примечания

Это возможно для конкретного аппаратного потока должен назначаться нескольких планировщиков, в то же время. Одна из причин может быть, что нет достаточно аппаратных потоков в системе для удовлетворения минимальной параллельности для всех планировщиков без общего доступа к ресурсам. Другой вариант — то, что ресурсы временно назначены другие планировщики когда планировщик-владелец не использует их, посредством его корни виртуального процессора на этом потоке оборудования.

Уровень подписки на аппаратный поток обозначается количество потоков подписки и активации корни виртуального процессора, связанные с этим потоком оборудования. С точки зрения определенного планировщика внешний уровень подписки аппаратного потока — это часть подписку, которую другие планировщики. Планировщику отправляются уведомления, что ресурсы извне заняты, при перемещении внешний уровень подписки для аппаратного потока с нуля в положительные значения.

Уведомления с помощью этого метода отправляются только планировщикам, которые имеют политику где значение `MinConcurrency` ключ политики равен значению для `MaxConcurrency` ключ политики. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).

Планировщик, доступны для уведомлений получает набор начального уведомления при его создании, сообщая ей, являются ли ресурсы, которые ему было присвоено извне занятости и неактивности.

##  <a name="notifyresourcesexternallyidle"></a>  Метод IScheduler::NotifyResourcesExternallyIdle

Уведомляет этот планировщик, аппаратных потоков, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другие планировщики.

```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Параметры

*ppVirtualProcessorRoots*<br/>
Массив `IVirtualProcessorRoot` интерфейсов, связанных с аппаратных потоков, на которых другие планировщики стали простоя.

*count*<br/>
Количество `IVirtualProcessorRoot` интерфейсов в массиве.

### <a name="remarks"></a>Примечания

Это возможно для конкретного аппаратного потока должен назначаться нескольких планировщиков, в то же время. Одна из причин может быть, что нет достаточно аппаратных потоков в системе для удовлетворения минимальной параллельности для всех планировщиков без общего доступа к ресурсам. Другой вариант — то, что ресурсы временно назначены другие планировщики когда планировщик-владелец не использует их, посредством его корни виртуального процессора на этом потоке оборудования.

Уровень подписки на аппаратный поток обозначается количество потоков подписки и активации корни виртуального процессора, связанные с этим потоком оборудования. С точки зрения определенного планировщика внешний уровень подписки аппаратного потока — это часть подписку, которую другие планировщики. Уведомления, что ресурсы извне заняты, посылаются планировщика, когда внешний уровень подписки для аппаратного потока падает до нуля из ранее положительного значения.

Уведомления с помощью этого метода отправляются только планировщикам, которые имеют политику где значение `MinConcurrency` ключ политики равен значению для `MaxConcurrency` ключ политики. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).

Планировщик, доступны для уведомлений получает набор начального уведомления при его создании, сообщая ей, являются ли ресурсы, которые ему было присвоено извне занятости и неактивности.

##  <a name="removevirtualprocessors"></a>  Метод IScheduler::RemoveVirtualProcessors

Инициирует удаление корни виртуального процессора, которые ранее были выделены данного планировщика.

```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Параметры

*ppVirtualProcessorRoots*<br/>
Массив `IVirtualProcessorRoot` интерфейсы, представляющий корни виртуального процессора для удаления.

*count*<br/>
Количество `IVirtualProcessorRoot` интерфейсов в массиве.

### <a name="remarks"></a>Примечания

Диспетчер ресурсов вызывает `RemoveVirtualProcessors` метод, чтобы использовать набор корневых виртуальных процессоров у планировщика. Планировщик должен вызвать [удалить](iexecutionresource-structure.md#remove) метод для каждого интерфейса, когда он закончила с корни виртуального процессора. Не используйте `IVirtualProcessorRoot` интерфейс после были активированы `Remove` для него метода.

Параметр `ppVirtualProcessorRoots` указывает на массив интерфейсов. Среди набора корни виртуального процессора для удаления, не были активированы корни возвращается немедленно с помощью `Remove` метод. Корни, которые были активированы и либо выполняют работу или были отключены и ожидают прибытия работы, должны возвращаться асинхронно. Планировщику необходимо сделать все возможное для удаления корневого виртуального процессора, как можно быстрее. Задержка удаления корней виртуального процессора может привести к непреднамеренной превышение лимита подписки в планировщике.

##  <a name="statistics"></a>  Метод IScheduler::Statistics

Предоставляет сведения, относящиеся к скорость прибытия и завершения задач и изменение длины очереди для планировщика.

```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>Параметры

*pTaskCompletionRate*<br/>
Число задач, осуществленных с момента последнего вызова этого метода в планировщике.

*pTaskArrivalRate*<br/>
Число задач, которые поступили в планировщик с момента последнего вызова этого метода.

*pNumberOfTasksEnqueued*<br/>
Общее число задач во всех очередях планировщика.

### <a name="remarks"></a>Примечания

Этот метод вызывается диспетчером ресурсов для сбора статистики для планировщика. Здесь собранная статистика будет использоваться для алгоритмов динамической обратной связи, чтобы определить, когда стоит назначить больше ресурсов планировщику и когда следует уяснить ресурсы. Значения, предоставленные планировщик может быть оптимистичный и не обязательно точно отражает текущее значение счетчика.

Необходимо реализовать этот метод, если требуется, чтобы диспетчер ресурсов использовал отзывы о таких действиях, как прибытие задачи, чтобы определить способ распределения ресурсов между данным планировщиком и другими планировщиками, зарегистрированными диспетчером ресурсов. Если вы решили не сбора статистики, можно задать ключ политики `DynamicProgressFeedback` значению `DynamicProgressFeedbackDisabled` в политике на планировщике и ресурс Manager не будет вызывать этот метод на планировщика.

В отсутствие статистические данные диспетчер ресурсов будет использовать уровни подписки потока оборудования для принятия ресурсов выделения и миграции решений. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Класс SchedulerPolicy](schedulerpolicy-class.md)<br/>
[Структура IExecutionContext](iexecutioncontext-structure.md)<br/>
[Структура IThreadProxy](ithreadproxy-structure.md)<br/>
[Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)<br/>
[Структура IResourceManager](iresourcemanager-structure.md)
