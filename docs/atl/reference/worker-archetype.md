---
title: Рабочий архетипа | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ff0e71e15c70d8d5d9dee0b398d4f0c075eb47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="worker-archetype"></a>Рабочий архетипа
Классы, которые соответствуют *рабочих* архетипа предоставить код для обработки рабочих элементов в очередь в пуле потоков.  
  
 **Реализация**  
  
 Реализовать класс, соответствующий этой архетипа, класс должен обеспечивать следующие возможности:  
  
|Метод|Описание|  
|------------|-----------------|  
|[Initialize](#initialize)|Вызывается для инициализации объекта работника перед все запросы передаются [Execute](#execute).|  
|[Выполнение](#execute)|Вызывается для обработки рабочего элемента.|  
|[Завершение](#terminate)|Вызван для после были переданы все запросы, отмена инициализации объекта рабочих [Execute](#execute).|  
  
|Typedef|Описание|  
|-------------|-----------------|  
|[RequestType](#requesttype)|Typedef для типа рабочего элемента, который может быть обработан с помощью класса worker.|  
  
 Типичный *рабочих* класса выглядит следующим образом:  
  
 [!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]  
  
 **Существующие реализации**  
  
 Эти классы соответствуют этой архетипа:  
  
|Класс|Описание|  
|-----------|-----------------|  
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|Получает запросы из пула потоков и передает их рабочий объект, который создается и уничтожается при каждом запросе.|  
  
 **Используйте**  
  
 Эти параметры шаблона ожидать класса для обеспечения соответствия этой архетипа:  
  
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
 Рабочий элемент должен быть обработан. Рабочий элемент имеет тот же тип, что `RequestType`.  
  
 `pvWorkerParam`  
 Настраиваемый параметр воспринимает класс worker. Также передается `WorkerArchetype::Initialize` и `Terminate`.  
  
 `pOverlapped`  
 Указатель на [OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) структура, используемая для создания очереди, на какие рабочие элементы были поставлены в очередь.  
  
## <a name="initialize"></a> WorkerArchetype::Initialize
Вызывается для инициализации объекта работника перед все запросы передаются `WorkerArchetype::Execute`.  
```
BOOL Initialize(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Параметры  
 `pvParam`  
 Настраиваемый параметр воспринимает класс worker. Также передается `WorkerArchetype::Terminate` и `WorkerArchetype::Execute`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Вернуть **TRUE** при успешном выполнении **FALSE** при сбое.  
  
## <a name="requesttype"></a> WorkerArchetype::RequestType
Typedef для типа рабочего элемента, который может быть обработан с помощью класса worker.  
  
```  
typedef MyRequestType RequestType;    
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип должен использоваться в качестве первого параметра `WorkerArchetype::Execute` и должен поддерживать приведение к и из ULONG_PTR.  
  
## <a name="terminate"></a> WorkerArchetype::Terminate
Вызван для после были переданы все запросы, отмена инициализации объекта рабочих `WorkerArchetype::Execute`).  
    
``` 
void Terminate(void* pvParam) throw();
```  
  
#### <a name="parameters"></a>Параметры  
 `pvParam`  
 Настраиваемый параметр воспринимает класс worker. Также передается `WorkerArchetype::Initialize` и `WorkerArchetype::Execute`.  
  
## <a name="see-also"></a>См. также  
 [Archetypes](../../atl/reference/atl-archetypes.md)   
 [Основные понятия](../../atl/active-template-library-atl-concepts.md)   
 [Компоненты ATL COM Desktop](../../atl/atl-com-desktop-components.md)



