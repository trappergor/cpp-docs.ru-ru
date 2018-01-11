---
title: "Структура IScheduler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords: IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c639bd760b837923f3011e9209d923fef31f8aee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ischeduler-structure"></a>Структура IScheduler
Интерфейс для абстракции планировщика работы. Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками работы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|Предоставляет планировщик с набором корней виртуальный процессор для его использования. Каждый `IVirtualProcessorRoot` интерфейс представляет право на выполнение одного потока, который может выполнять работу от имени планировщик.|  
|[IScheduler::GetId](#getid)|Возвращает уникальный идентификатор для планировщика.|  
|[IScheduler::GetPolicy](#getpolicy)|Возвращает копию политики планировщика. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).|  
|[IScheduler::NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Уведомляет этот планировщик, на аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другими планировщики.|  
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Уведомляет этот планировщик, на аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другими планировщики.|  
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|Инициирует Удаление корней виртуального процессора, которые ранее были выделены на данном планировщике.|  
|[IScheduler::Statistics](#statistics)|Предоставляет сведения о скорости поступления до завершения задачи и изменение длины очереди для планировщика.|  
  
## <a name="remarks"></a>Примечания  
 При реализации пользовательских планировщика, который взаимодействует с диспетчером ресурсов, необходимо предоставить реализацию `IScheduler` интерфейса. Этот интерфейс — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов. Представленный другой конец `IResourceManager` и `ISchedulerProxy` интерфейсы, используемые диспетчером ресурсов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IScheduler`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="addvirtualprocessors"></a>Метод IScheduler::AddVirtualProcessors  
 Предоставляет планировщик с набором корней виртуальный процессор для его использования. Каждый `IVirtualProcessorRoot` интерфейс представляет право на выполнение одного потока, который может выполнять работу от имени планировщик.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсов, представляющих виртуальных корней, добавляемый в планировщике.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсы в массиве.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер ресурсов вызывает `AddVirtualProcessor` метод для предоставления первоначального набора корней виртуальный процессор в планировщике. Он также может вызывать метод для добавления корней виртуальный процессор в планировщике при перебалансировке ресурсов между планировщиками.  
  
##  <a name="getid"></a>Метод IScheduler::GetId  
 Возвращает уникальный идентификатор для планировщика.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный целочисленный идентификатор.  
  
### <a name="remarks"></a>Примечания  
 Следует использовать [GetSchedulerId](concurrency-namespace-functions.md) функцию для получения уникального идентификатора для объекта, который реализует `IScheduler` интерфейс, прежде чем использовать интерфейс в качестве параметра в методы, предоставленные диспетчером ресурсов. Вы должны возвращать тот же идентификатор при `GetId` вызове функции.  
  
 Идентификатор, полученный из другого источника может привести к неопределенному поведению.  
  
##  <a name="getpolicy"></a>Метод IScheduler::GetPolicy  
 Возвращает копию политики планировщика. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия политики планировщика.  
  
##  <a name="notifyresourcesexternallybusy"></a>Метод IScheduler::NotifyResourcesExternallyBusy  
 Уведомляет этот планировщик, на аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другими планировщики.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсов, связанных с потоками оборудования, на которых другие планировщики стали занят.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсы в массиве.  
  
### <a name="remarks"></a>Примечания  
 Существует возможность для определенного аппаратного потока должен назначаться несколько планировщиков в то же время. Одна из причин для этого может быть, что не отсутствуют достаточно аппаратных потоков на компьютере, чтобы соответствующие минимальной параллельности для всех планировщиков без общего доступа к ресурсам. Другая возможность заключается в том, что ресурсы временно присваиваются другими планировщиками, когда планировщик-владелец не использует их, посредством его корни виртуального процессора в этом потоке оборудования.  
  
 Уровень подписки аппаратного потока обозначается количеством подписанных потоков и активированных корней виртуального процессора, связанных с потоком оборудования. С точки зрения определенного планировщика уровень внешней подписки аппаратного потока — часть подписку, которую другие планировщики. При перемещении внешний уровень подписки для аппаратного потока с нуля в положительные значения планировщика отправляются уведомления, что ресурсы извне заняты.  
  
 Уведомления через этот метод только отправляются планировщикам, которые содержат политику где значение `MinConcurrency` равно значению для ключа политики `MaxConcurrency` ключ политики. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Планировщик, который имеет право на уведомления возвращает набор начального уведомления при его создании, информирования о его ли ресурсы, которые она была присвоена извне занятости и неактивности.  
  
##  <a name="notifyresourcesexternallyidle"></a>Метод IScheduler::NotifyResourcesExternallyIdle  
 Уведомляет этот планировщик, на аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другими планировщики.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсов, связанных с потоками оборудования, на которых другие планировщики стали простаивать.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсы в массиве.  
  
### <a name="remarks"></a>Примечания  
 Существует возможность для определенного аппаратного потока должен назначаться несколько планировщиков в то же время. Одна из причин для этого может быть, что не отсутствуют достаточно аппаратных потоков на компьютере, чтобы соответствующие минимальной параллельности для всех планировщиков без общего доступа к ресурсам. Другая возможность заключается в том, что ресурсы временно присваиваются другими планировщиками, когда планировщик-владелец не использует их, посредством его корни виртуального процессора в этом потоке оборудования.  
  
 Уровень подписки аппаратного потока обозначается количеством подписанных потоков и активированных корней виртуального процессора, связанных с потоком оборудования. С точки зрения определенного планировщика уровень внешней подписки аппаратного потока — часть подписку, которую другие планировщики. Уведомления, что ресурсы извне заняты отправляются планировщика, когда внешний уровень подписки на аппаратный поток становится равным нулю из ранее положительного значения.  
  
 Уведомления через этот метод только отправляются планировщикам, которые содержат политику где значение `MinConcurrency` равно значению для ключа политики `MaxConcurrency` ключ политики. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Планировщик, который имеет право на уведомления возвращает набор начального уведомления при его создании, информирования о его ли ресурсы, которые она была присвоена извне занятости и неактивности.  
  
##  <a name="removevirtualprocessors"></a>Метод IScheduler::RemoveVirtualProcessors  
 Инициирует Удаление корней виртуального процессора, которые ранее были выделены на данном планировщике.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсы, представляющий корни виртуального процессора для удаления.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсы в массиве.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер ресурсов вызывает `RemoveVirtualProcessors` метод, чтобы использовать набор корней виртуальный процессор из планировщика. Планировщик должен вызвать [удалить](iexecutionresource-structure.md#remove) метод для каждого интерфейса, при завершении работы с корни виртуального процессора. Не используйте `IVirtualProcessorRoot` интерфейса после вызванными `Remove` метода.  
  
 Параметр `ppVirtualProcessorRoots` указывает на массив интерфейсов. Входит в набор корни виртуального процессора для удаления корни не был активирован возвращается немедленно с помощью `Remove` метод. Корни, которые были активированы и либо выполняют работу или были отключены и ожидают прибытия работы, должны возвращаться асинхронно. Планировщику необходимо сделать все попытки удалить корневой виртуальный процессор, как можно быстрее. Задержка удаления корней виртуального процессора может привести к непреднамеренному превышение лимита подписки в планировщике.  
  
##  <a name="statistics"></a>Метод IScheduler::Statistics  
 Предоставляет сведения о скорости поступления до завершения задачи и изменение длины очереди для планировщика.  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pTaskCompletionRate`  
 Число задач, осуществленных с момента последнего вызова этого метода планировщиком.  
  
 `pTaskArrivalRate`  
 Число задач, которые поступили в планировщик с момента последнего вызова этого метода.  
  
 `pNumberOfTasksEnqueued`  
 Общее число задач во всех очередях планировщика.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается диспетчером ресурсов для сбора статистики для планировщика. Здесь собранная статистика будет использоваться для алгоритмов динамической обратной связи, чтобы определить, когда стоит назначить больше ресурсов планировщику и когда следует забрать ресурсы. Значения, предоставленные планировщиком может быть оптимистичный и не обязательно точно отражать текущее значение счетчика.  
  
 Необходимо реализовать этот метод, если требуется, чтобы диспетчер ресурсов использовал отзывы о таких действиях, как прибытие задачи, чтобы определить способ распределения ресурсов между данным планировщиком и другими планировщиками, зарегистрированными диспетчером ресурсов. Если вы решили не сбора статистики, можно задать ключ политики `DynamicProgressFeedback` значение `DynamicProgressFeedbackDisabled` в политике данным планировщиком и ресурса Manager не будет вызывать этот метод на планировщика.  
  
 В отсутствие статистические данные диспетчер ресурсов будет использовать уровни подписки потока оборудования для принятия решений по распределения и миграции ресурсов. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Класс SchedulerPolicy](schedulerpolicy-class.md)   
 [Структура IExecutionContext](iexecutioncontext-structure.md)   
 [Структура IThreadProxy](ithreadproxy-structure.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)   
 [Структура IResourceManager](iresourcemanager-structure.md)
