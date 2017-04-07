---
title: "Класс CNonStatelessWorker | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
caps.latest.revision: 21
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 804b87bf752aac5cecf64cb61b4d53d6269963f2
ms.lasthandoff: 02/24/2017

---
# <a name="cnonstatelessworker-class"></a>Класс CNonStatelessWorker
Получает запросы из пула потоков и передает их рабочий объект, который создается и уничтожается при каждом запросе.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>Параметры  
 *Работник*  
 Рабочий поток класс, соблюдения [архетипа рабочей](../../atl/reference/worker-archetype.md) подходит для обработки запросов в очереди на [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|Реализация [WorkerArchetype::Execute](worker-archetype.md#execute).|  
|[CNonStatelessWorker::Initialize](#initialize)|Реализация [WorkerArchetype::Initialize](worker-archetype.md#initialize).|  
|[CNonStatelessWorker::Terminate](#terminate)|Реализация [WorkerArchetype::Terminate](worker-archetype.md#terminate).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является простой рабочий поток для использования с [CThreadPool](../../atl/reference/cthreadpool-class.md). Этот класс не предоставляет все возможности обработки запросов свои собственные. Вместо этого он создает один экземпляр *рабочей* за один запрос и делегирует реализацию его методов для этого экземпляра.  
  
 Преимущество этого класса заключается в том, что он предоставляет удобный способ для изменения существующих классов рабочих потоков модель состояний. `CThreadPool`будет создан один рабочий в течение времени существования потока, если рабочий класс хранит состояние, он будет содержать нескольких запросах. Просто обернуть этого класса в `CNonStatelessWorker` шаблона перед его с использованием `CThreadPool`, время жизни работника и состояния, он содержит только один запрос.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
##  <a name="execute"></a>CNonStatelessWorker::Execute  
 Реализация [WorkerArchetype::Execute](worker-archetype.md#execute).  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает экземпляр *рабочей* класса на стек и вызывает метод [инициализации](worker-archetype.md#initialize) для этого объекта. Если инициализация прошла успешно, этот метод также вызывает [Execute](worker-archetype.md#execute) и [завершения](worker-archetype.md#terminate) на тот же объект.  

  
##  <a name="initialize"></a>CNonStatelessWorker::Initialize  
 Реализация [WorkerArchetype::Initialize](worker-archetype.md#initialize).  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение TRUE.  
  
### <a name="remarks"></a>Примечания  
 Этот класс не выполняет инициализацию `Initialize`.  
  
##  <a name="requesttype"></a>CNonStatelessWorker::RequestType  
 Реализация [WorkerArchetype::RequestType](worker-archetype.md#requesttype).  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс выполняет того же типа рабочего элемента, что класс, используемый для *рабочей* параметр шаблона. В разделе [CNonStatelessWorker Обзор](../../atl/reference/cnonstatelessworker-class.md) подробные сведения.  
  
##  <a name="terminate"></a>CNonStatelessWorker::Terminate  
 Реализация [WorkerArchetype::Terminate](worker-archetype.md#terminate).  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>Примечания  
 Этот класс не производит очистку `Terminate`.  
  
## <a name="see-also"></a>См. также  
 [Класс CThreadPool](../../atl/reference/cthreadpool-class.md)   
 [Архитектура рабочих](../../atl/reference/worker-archetype.md)   
 [Классы](../../atl/reference/atl-classes.md)

