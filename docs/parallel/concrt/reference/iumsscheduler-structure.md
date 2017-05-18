---
title: "Структура IUMSScheduler | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 58ca59224b5d9cdeb282562349642736a1b22c74
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="iumsscheduler-structure"></a>Структура IUMSScheduler
Интерфейс абстракции планировщика, которому требуется, чтобы диспетчер ресурсов среды выполнения с параллелизмом передал ему потоки планировщика в пользовательском режиме (UMS). Диспетчер ресурсов среды выполнения с параллелизмом использует этот интерфейс для взаимодействия с планировщиками потоков UMS. Интерфейс `IUMSScheduler` наследует от интерфейса `IScheduler`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Назначает `IUMSCompletionList` интерфейс в планировщике потоков UMS.|  
  
## <a name="remarks"></a>Примечания  
 При реализации пользовательских планировщика, который взаимодействует с диспетчером ресурсов, и требуется, чтобы потоки UMS передавались планировщику вместо обычных потоков Win32, необходимо предоставить реализацию `IUMSScheduler` интерфейса. Кроме того, следует задать значение политики для ключа политики планировщика `SchedulerKind` быть `UmsThreadDefault`. Если параметр политики указывает потока UMS `IScheduler` интерфейс, который передается в качестве параметра [IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler) метод должен быть `IUMSScheduler` интерфейса.  
  
 Диспетчер ресурсов может передать потоки UMS только в операционных системах, поддерживающих UMS. 64-разрядных операционных системах с версией Windows 7 и выше поддерживают потоки UMS. При создании политики планировщика с `SchedulerKind` ключа задано значение `UmsThreadDefault` и базовой платформы поддерживает UMS значение `SchedulerKind` ключ для этой политики будет изменено на значение `ThreadScheduler`. Следует всегда читать обратно значение этой политики перед ожидать получения потоков UMS.  
  
 `IUMSScheduler` Интерфейс — это один конец двустороннего канала связи между планировщиком и диспетчер ресурсов. Представленный другой конец `IResourceManager` и `ISchedulerProxy` интерфейсы, используемые диспетчером ресурсов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="setcompletionlist"></a>Метод IUMSScheduler::SetCompletionList  
 Назначает `IUMSCompletionList` интерфейс в планировщике потоков UMS.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `pCompletionList`  
 Интерфейс списка завершения для планировщика. Имеется один список для каждого планировщика.  
  
### <a name="remarks"></a>Примечания  
 Диспетчер ресурсов будет вызывать этот метод на планировщика, который указывает, что ему нужны UMS-потоки, после того, планировщик запросил начального распределения ресурсов. Можно использовать планировщик `IUMSCompletionList` интерфейс, чтобы определить, когда разблокировать UMS прокси-поток. Он допустим только для доступа к этот интерфейс из прокси потоков, выполняющихся на корневой виртуальный процессор, присвоенный планировщику UMS.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Структура IScheduler](ischeduler-structure.md)   
 [Структура IUMSCompletionList](iumscompletionlist-structure.md)   
 [Структура IResourceManager](iresourcemanager-structure.md)

