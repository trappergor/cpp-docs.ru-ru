---
title: "Архитектура рабочих | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 046160644cca3bd23e4293a3c52692d2b4c94cd5
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="worker-archetype"></a>Архитектура рабочих
Классы, которые соответствуют *рабочей* архетипа предоставить код для обработки рабочих элементов в очередь в пуле потоков.  
  
 **Реализация**  
  
 Для реализации класса, соответствующие этой архетипа, класс должен предоставлять следующие возможности:  
  
|Метод|Описание|  
|------------|-----------------|  
|[Инициализация](#initialize)|Вызывается для инициализации рабочий объект, прежде чем все запросы передаются [Execute](#execute).|  
|[Выполнение](#execute)|Вызывается для обработки рабочего элемента.|  
|[Завершить](#terminate)|Вызван для отмены инициализации рабочий объект после передачи всех запросов [Execute](#execute).|  
  
|Typedef|Описание|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Typedef для типа рабочего элемента, который может быть обработан с помощью класса рабочей.|  
  
 Типичный *рабочей* класса выглядит следующим образом:  
  
 [!code-cpp[NVC_ATL_Utilities&#137;](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Существующие реализации**  
  
 Эти классы соответствуют этой архетипа:  
  
|Класс|Описание|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их рабочий объект, который создается и уничтожается при каждом запросе.|  
  
 **Использование**  
  
 Эти параметры шаблона ожидают, что класс, чтобы соответствовать этой архетипа:  
  
|Имя параметра|Где используется|  
|--------------------|-------------|  
|*Работник*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|  
|*Работник*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** файлов atlutil.h  
  
## <a name="execute"></a>WorkerArchetype::Execute
Вызывается для обработки рабочего элемента.  
  
  
  
```  
void Execute(
    RequestType request,  
    void* pvWorkerParam,  
    OVERLAPPED* pOverlapped);
```  
  
#### <a name="parameters"></a>Параметры  
 `request`  
 Рабочий элемент для обработки. Рабочий элемент имеет тот же тип, что `RequestType`.  
  
 `pvWorkerParam`  
 Настраиваемый параметр поняты рабочий класс. Также передается `WorkerArchetype::Initialize` и `Terminate`.  
  
 `pOverlapped`  
 Указатель на [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) структура, используемая для создания очереди, на какие рабочие элементы были поставлены в очередь.  
  
## <a name="initialize"></a>WorkerArchetype::Initialize
Вызывается для инициализации рабочий объект, прежде чем все запросы передаются `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Параметры  
 `pvParam`  
 Настраиваемый параметр поняты рабочий класс. Также передается `WorkerArchetype::Terminate` и `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вернуть **TRUE** в случае успешного выполнения **FALSE** в случае сбоя.  
  
## <a name="requesttype"></a>WorkerArchetype::RequestType
Typedef для типа рабочего элемента, который может быть обработан с помощью класса рабочей.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип должен использоваться в качестве первого параметра `WorkerArchetype::Execute` и должно быть способно, приводимый в и из ULONG_PTR.  
  
## <a name="terminate"></a>WorkerArchetype::Terminate
Вызван для отмены инициализации рабочий объект после передачи всех запросов `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Параметры  
 `pvParam`  
 Настраиваемый параметр поняты рабочий класс. Также передается `WorkerArchetype::Initialize` и `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>См. также  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты COM Desktop ATL](../../atl/atl-com-desktop-components.md)




