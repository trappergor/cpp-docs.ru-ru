---
title: "Структура IScheduler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IScheduler
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
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
ms.openlocfilehash: fd8733bdcf113497b82cb2559eaba5a6a4a15165
ms.lasthandoff: 02/24/2017

---
# <a name="ischeduler-structure"></a>Структура IScheduler
Интерфейс для абстракции планировщика работы. Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками работы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод IScheduler::AddVirtualProcessors](#addvirtualprocessors)|Предоставляет планировщик с набором корней виртуальный процессор для его использования. Каждый `IVirtualProcessorRoot` интерфейс представляет право на выполнение одного потока, которые выполняют работы от имени планировщик.|  
|[Метод IScheduler::GetId](#getid)|Возвращает уникальный идентификатор для планировщика.|  
|[Метод IScheduler::GetPolicy](#getpolicy)|Возвращает копию политики планировщика. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).|  
|[Метод IScheduler::NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Уведомляет этот планировщик, что аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другие планировщики.|  
|[Метод IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Уведомляет этот планировщик, что аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другие планировщики.|  
|[Метод IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|Инициирует удаление корни виртуального процессора, ранее выделенные для этого планировщика.|  
|[Метод IScheduler::Statistics](#statistics)|Предоставляет сведения о скорости поступления до завершения задачи и изменение длины очереди для планировщика.|  
  
## <a name="remarks"></a>Примечания  
 При реализации пользовательских планировщика, который взаимодействует с диспетчером ресурсов, должны предоставлять реализацию метода `IScheduler` интерфейса. Этот интерфейс — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов. Представленный другой конец `IResourceManager` и `ISchedulerProxy` интерфейсы, используемые диспетчером ресурсов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IScheduler`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameaddvirtualprocessorsa--ischeduleraddvirtualprocessors-method"></a><a name="addvirtualprocessors"></a>Метод IScheduler::AddVirtualProcessors  
 Предоставляет планировщик с набором корней виртуальный процессор для его использования. Каждый `IVirtualProcessorRoot` интерфейс представляет право на выполнение одного потока, которые выполняют работы от имени планировщик.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` корней интерфейсов, представляющих виртуального процессора, добавляемого в планировщике.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсов в массиве.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер ресурсов вызывает `AddVirtualProcessor` метод для предоставления первоначального набора корней виртуальный процессор планировщику. Он также может вызывать этот метод для добавления к планировщику корни виртуального процессора при перебалансировке ресурсов между планировщиками.  
  
##  <a name="a-namegetida--ischedulergetid-method"></a><a name="getid"></a>Метод IScheduler::GetId  
 Возвращает уникальный идентификатор для планировщика.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный целочисленный идентификатор.  
  
### <a name="remarks"></a>Примечания  
 Следует использовать [GetSchedulerId](concurrency-namespace-functions.md) функцию для получения уникального идентификатора для объекта, который реализует `IScheduler` интерфейс, прежде чем использовать интерфейс как параметр методам указано диспетчером ресурсов. Вы должны возвращать тот же идентификатор при `GetId` вызывается функция.  
  
 Идентификатор, полученный из другого источника может привести к неопределенному поведению.  
  
##  <a name="a-namegetpolicya--ischedulergetpolicy-method"></a><a name="getpolicy"></a>Метод IScheduler::GetPolicy  
 Возвращает копию политики планировщика. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Копия политики планировщика.  
  
##  <a name="a-namenotifyresourcesexternallybusya--ischedulernotifyresourcesexternallybusy-method"></a><a name="notifyresourcesexternallybusy"></a>Метод IScheduler::NotifyResourcesExternallyBusy  
 Уведомляет этот планировщик, что аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` теперь используются другие планировщики.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсов, связанных с потоками оборудования, на которых другие планировщики стали занят.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсов в массиве.  
  
### <a name="remarks"></a>Примечания  
 Существует возможность для определенного аппаратного потока должен назначаться несколькими планировщиками в то же время. Одна из причин для этого может быть, не достаточно аппаратных потоков в системе, чтобы удовлетворять минимальным параллелизма для всех планировщиков без совместного использования ресурсов. Другая возможность заключается, что ресурсы временно назначаются другим планировщики когда планировщик-владелец не использует их, посредством его корней виртуального процессора в этом потоке оборудования.  
  
 Уровень подписки аппаратного потока обозначается количеством подписанных потоков и активированных корней виртуального процессора, связанных с потоком оборудования. С точки зрения конкретного планировщика уровень внешней подписки аппаратного потока — это часть подписки, которую другие планировщики. Планировщик отправляются уведомления, что ресурсы извне заняты, когда внешний уровень подписки на аппаратный поток смещается с нуля в положительные значения.  
  
 Уведомления через этот метод только отправляются планировщикам, имеющим политику где значение `MinConcurrency` политики ключ равен значению для `MaxConcurrency` ключ политики. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Планировщик, который определяет для уведомлений получает набор начального уведомления при его создании, сообщая ей, являются ли ресурсы, которые она была присвоена извне занятости и неактивности.  
  
##  <a name="a-namenotifyresourcesexternallyidlea--ischedulernotifyresourcesexternallyidle-method"></a><a name="notifyresourcesexternallyidle"></a>Метод IScheduler::NotifyResourcesExternallyIdle  
 Уведомляет этот планировщик, что аппаратные потоки, представленных набором корней виртуальный процессор в массиве `ppVirtualProcessorRoots` не используются другие планировщики.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсов, связанных с потоками оборудования, на которых другие планировщики стали простаивать.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсов в массиве.  
  
### <a name="remarks"></a>Примечания  
 Существует возможность для определенного аппаратного потока должен назначаться несколькими планировщиками в то же время. Одна из причин для этого может быть, не достаточно аппаратных потоков в системе, чтобы удовлетворять минимальным параллелизма для всех планировщиков без совместного использования ресурсов. Другая возможность заключается, что ресурсы временно назначаются другим планировщики когда планировщик-владелец не использует их, посредством его корней виртуального процессора в этом потоке оборудования.  
  
 Уровень подписки аппаратного потока обозначается количеством подписанных потоков и активированных корней виртуального процессора, связанных с потоком оборудования. С точки зрения конкретного планировщика уровень внешней подписки аппаратного потока — это часть подписки, которую другие планировщики. Планировщик отправляются уведомления, что ресурсы извне заняты, когда внешний уровень подписки на аппаратный поток падает до нуля из ранее положительного значения.  
  
 Уведомления через этот метод только отправляются планировщикам, имеющим политику где значение `MinConcurrency` политики ключ равен значению для `MaxConcurrency` ключ политики. Дополнительные сведения о политиках планировщиков см. в разделе [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Планировщик, который определяет для уведомлений получает набор начального уведомления при его создании, сообщая ей, являются ли ресурсы, которые она была присвоена извне занятости и неактивности.  
  
##  <a name="a-nameremovevirtualprocessorsa--ischedulerremovevirtualprocessors-method"></a><a name="removevirtualprocessors"></a>Метод IScheduler::RemoveVirtualProcessors  
 Инициирует удаление корни виртуального процессора, ранее выделенные для этого планировщика.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `ppVirtualProcessorRoots`  
 Массив `IVirtualProcessorRoot` интерфейсы, представляющий корни виртуального процессора, должны быть удалены.  
  
 `count`  
 Количество `IVirtualProcessorRoot` интерфейсов в массиве.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер ресурсов вызывает `RemoveVirtualProcessors` метод, чтобы забрать набор корней виртуальный процессор из планировщика. Планировщик должен вызывать [удаление](iexecutionresource-structure.md#remove) метод на каждом интерфейсе при завершении корни виртуального процессора. Не используйте `IVirtualProcessorRoot` интерфейс, когда были активированы `Remove` метод.  
  
 Параметр `ppVirtualProcessorRoots` указывает на массив интерфейсов. Среди набора корни виртуального процессора, должны быть удалены, не были активированы корни возвращается немедленно с помощью `Remove` метод. Корни, которые были активированы и либо выполняют работу или были отключены и ожидают прибытия работы, должны возвращаться асинхронно. Планировщику необходимо сделать все попытки удалить корень виртуального процессора как можно быстрее. Задержка удаления корней виртуального процессора может привести к непреднамеренному превышение лимита подписки в планировщике.  
  
##  <a name="a-namestatisticsa--ischedulerstatistics-method"></a><a name="statistics"></a>Метод IScheduler::Statistics  
 Предоставляет сведения о скорости поступления до завершения задачи и изменение длины очереди для планировщика.  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pTaskCompletionRate`  
 Число задач, которые были завершены планировщиком с момента последнего вызова этого метода.  
  
 `pTaskArrivalRate`  
 Число задач, которые поступили в планировщик с момента последнего вызова этого метода.  
  
 `pNumberOfTasksEnqueued`  
 Общее число задач во всех очередях планировщика.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается диспетчером ресурсов для сбора статистики для планировщика. Здесь собранная статистика будет использоваться для алгоритмов динамической обратной связи для определения, когда стоит назначить больше ресурсов планировщику и когда следует забрать ресурсы. Значения, предоставленные планировщиком может быть оптимистичный и не обязательно точно отражать текущее значение счетчика.  
  
 Необходимо реализовать этот метод, если требуется, чтобы диспетчер ресурсов использовал отзывы о таких действиях, как прибытие задачи, чтобы определить способ распределения ресурсов между данным планировщиком и другими планировщиками, зарегистрированными диспетчером ресурсов. Если сбор статистики не выбрана, можно задать ключ политики `DynamicProgressFeedback` значение `DynamicProgressFeedbackDisabled` в ваш планировщик политики и ресурс Manager не будет вызывать этот метод на планировщика.  
  
 В отсутствие статистические данные диспетчер ресурсов будет использовать уровни подписки потока оборудования для принятия решений по распределения и миграции ресурсов. Дополнительные сведения об уровнях подписки см. в разделе [IExecutionResource::CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Перечисление PolicyElementKey](concurrency-namespace-enums.md)   
 [Класс SchedulerPolicy](schedulerpolicy-class.md)   
 [Структура IExecutionContext](iexecutioncontext-structure.md)   
 [Структура IThreadProxy](ithreadproxy-structure.md)   
 [Структура IVirtualProcessorRoot](ivirtualprocessorroot-structure.md)   
 [Структура IResourceManager](iresourcemanager-structure.md)

