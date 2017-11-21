---
title: "Структура IExecutionContext | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
dev_langs: C++
helpviewer_keywords: IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: af687c482ee3565d7b350672b83291194a2edf44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="iexecutioncontext-structure"></a>Структура IExecutionContext
Интерфейс для контекста выполнения, который может выполняться на данном виртуальном процессоре и к которому может применяться совместное переключение контекста.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IExecutionContext::Dispatch](#dispatch)|Метод, который вызывается, когда прокси-поток запускает выполнение определенного контекста выполнения. Это должен быть основной рабочий процесс для вашего планировщика.|  
|[IExecutionContext::GetId](#getid)|Возвращает уникальный идентификатор для контекста выполнения.|  
|[IExecutionContext::GetProxy](#getproxy)|Возвращает интерфейс для прокси потока, выполняющего данный контекст.|  
|[IExecutionContext::GetScheduler](#getscheduler)|Возвращает интерфейс планировщика, к которой принадлежит этот контекст выполнения.|  
|[IExecutionContext::SetProxy](#setproxy)|Связывает прокси-поток с данного контекста выполнения. Связанный прокси-поток вызывает этот метод прямо до начала выполнения контекста `Dispatch` метод.|  
  
## <a name="remarks"></a>Примечания  
 При реализации пользовательских планировщика, который взаимодействует с диспетчером ресурсов среда выполнения с параллелизмом, необходимо реализовать `IExecutionContext` интерфейса. Потоки, созданные диспетчером ресурсов работать от имени вашего планировщика, выполнив `IExecutionContext::Dispatch` метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IExecutionContext`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="dispatch"></a>Метод IExecutionContext::Dispatch  
 Метод, который вызывается, когда прокси-поток запускает выполнение определенного контекста выполнения. Это должен быть основной рабочий процесс для вашего планировщика.  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pDispatchState`  
 Указатель на состояние, под которым отправляется этот контекст выполнения. Дополнительные сведения о состоянии диспетчеризации см. в разделе [DispatchState](dispatchstate-structure.md).  
  
##  <a name="getid"></a>Метод IExecutionContext::GetId  
 Возвращает уникальный идентификатор для контекста выполнения.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный целочисленный идентификатор.  
  
### <a name="remarks"></a>Примечания  
 Следует использовать метод `GetExecutionContextId` получить уникальный идентификатор для объекта, который реализует `IExecutionContext` интерфейс, прежде чем использовать интерфейс в качестве параметра в методы, предоставленные диспетчером ресурсов. Вы должны возвращать тот же идентификатор при `GetId` вызове функции.  
  
 Идентификатор, полученный из другого источника может привести к неопределенному поведению.  
  
##  <a name="getproxy"></a>Метод IExecutionContext::GetProxy  
 Возвращает интерфейс для прокси потока, выполняющего данный контекст.  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс `IThreadProxy`. Если прокси-поток контекста выполнения не был инициализирован с помощью вызова `SetProxy`, эта функция должна возвращать `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер ресурсов будет вызывать `SetProxy` метод в контексте выполнения с `IThreadProxy` интерфейс в качестве параметра, прежде чем входить `Dispatch` метод для контекста. Ожидается, что пользователь для хранения этого аргумента и возвращение его при вызове для `GetProxy()`.  
  
##  <a name="getscheduler"></a>Метод IExecutionContext::GetScheduler  
 Возвращает интерфейс планировщика, к которой принадлежит этот контекст выполнения.  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс `IScheduler`.  
  
### <a name="remarks"></a>Примечания  
 Необходимо инициализировать контекст выполнения с допустимым `IScheduler` интерфейс, прежде чем использовать его как параметр в методы, предоставленные диспетчером ресурсов.  
  
##  <a name="setproxy"></a>Метод IExecutionContext::SetProxy  
 Связывает прокси-поток с данного контекста выполнения. Связанный прокси-поток вызывает этот метод прямо до начала выполнения контекста `Dispatch` метод.  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pThreadProxy`  
 Интерфейс для прокси-поток, который собирается перейти `Dispatch` метода в данном контексте выполнения.  
  
### <a name="remarks"></a>Примечания  
 Ожидается, что пользователь для сохранения параметра `pThreadProxy` и вернуть его во время вызова `GetProxy` метод. Диспетчер ресурсов гарантирует, что прокси-поток, связанный с контекстом выполнения не изменится во время выполнения прокси-поток `Dispatch` метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IScheduler](ischeduler-structure.md)   
 [Структура IThreadProxy](ithreadproxy-structure.md)
