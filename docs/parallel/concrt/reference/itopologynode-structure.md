---
title: "Структура ITopologyNode | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
dev_langs: C++
helpviewer_keywords: ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c2e989dca783e90d975bd46a6f5f44cdfa469ef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="itopologynode-structure"></a>Структура ITopologyNode
Интерфейс для узла топологии, как определено диспетчером ресурсов. Узел содержит один или несколько ресурсов выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|Возвращает количество ресурсов выполнения, сгруппированных в этом узле.|  
|[ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.|  
|[ITopologyNode::GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного узла.|  
|[ITopologyNode::GetNext](#getnext)|Возвращает интерфейс следующего узла топологии в порядке перечисления.|  
|[ITopologyNode::GetNumaNode](#getnumanode)|Возвращает Windows назначенный номер узла NUMA, к которому относится данный узел которые ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 Обычно этот интерфейс используется для прохода топологии системы, что наблюдается диспетчером ресурсов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ITopologyNode`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getexecutionresourcecount"></a>Метод ITopologyNode::GetExecutionResourceCount  
 Возвращает количество ресурсов выполнения, сгруппированных в этом узле.  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество ресурсов выполнения, сгруппированных в этом узле.  
  
##  <a name="getfirstexecutionresource"></a>Метод ITopologyNode::GetFirstExecutionResource  
 Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.  
  
##  <a name="getid"></a>Метод ITopologyNode::GetId  
 Возвращает уникальный идентификатор диспетчера ресурсов для данного узла.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор диспетчера ресурсов для данного узла.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения с параллелизмом предоставляет аппаратных потоков в группах узлов процессора в системе. Узлы обычно являются производными от топологии оборудования системы. Например все процессоры на определенном сокете или определенном узле NUMA могут входить в одном узле процессора. Диспетчер ресурсов присваивает уникальные идентификаторы для этих узлов, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее число узлов процессора в системе.  
  
 Количество узлов, которые могут быть получены из функции [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="getnext"></a>Метод ITopologyNode::GetNext  
 Возвращает интерфейс следующего узла топологии в порядке перечисления.  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс следующего узла в порядке перечисления. Если в порядке перечисления топологии системы больше нет узлов, этот метод возвращает значение `NULL`.  
  
##  <a name="getnumanode"></a>Метод ITopologyNode::GetNumaNode  
 Возвращает Windows назначенный номер узла NUMA, к которому относится данный узел которые ресурсов.  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Windows назначенный номер узла NUMA, к которому относится данный узел диспетчера ресурсов.  
  
### <a name="remarks"></a>Примечания  
 Прокси потоков, выполняющихся на корневом виртуальном процессоре, принадлежащих этому узлу будет иметь сходства по крайней мере до уровня узла NUMA для узла NUMA, возвращаемый этим методом.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
