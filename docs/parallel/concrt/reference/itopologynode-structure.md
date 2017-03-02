---
title: "Структура ITopologyNode | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::ITopologyNode
dev_langs:
- C++
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
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
ms.openlocfilehash: 8274da148f9f74cad73d63363bbbaff307943539
ms.lasthandoff: 02/24/2017

---
# <a name="itopologynode-structure"></a>Структура ITopologyNode
Интерфейс для узла топологии, как определено диспетчером ресурсов. Узел содержит один или несколько ресурсов выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|Возвращает количество ресурсов выполнения, сгруппированных в этом узле.|  
|[Метод ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.|  
|[Метод ITopologyNode::GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного узла.|  
|[Метод ITopologyNode::GetNext](#getnext)|Возвращает интерфейс следующего узла топологии в порядке перечисления.|  
|[Метод ITopologyNode::GetNumaNode](#getnumanode)|Возвращает Windows назначенный номер узла NUMA, к которому принадлежит данный узел которые ресурсов.|  
  
## <a name="remarks"></a>Примечания  
 Обычно этот интерфейс используется для обхода топологии системы соблюдения диспетчером ресурсов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ITopologyNode`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namegetexecutionresourcecounta--itopologynodegetexecutionresourcecount-method"></a><a name="getexecutionresourcecount"></a>Метод ITopologyNode::GetExecutionResourceCount  
 Возвращает количество ресурсов выполнения, сгруппированных в этом узле.  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Количество ресурсов выполнения, сгруппированных в этом узле.  
  
##  <a name="a-namegetfirstexecutionresourcea--itopologynodegetfirstexecutionresource-method"></a><a name="getfirstexecutionresource"></a>Метод ITopologyNode::GetFirstExecutionResource  
 Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.  
  
##  <a name="a-namegetida--itopologynodegetid-method"></a><a name="getid"></a>Метод ITopologyNode::GetId  
 Возвращает уникальный идентификатор диспетчера ресурсов для данного узла.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Уникальный идентификатор диспетчера ресурсов для данного узла.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения с параллелизмом предоставляет аппаратных потоков в группах узлов процессора в системе. Узлы обычно являются производными от топологии оборудования системы. Например все процессоры на определенном сокете или определенном узле NUMA могут принадлежать к одному узлу процессора. Диспетчер ресурсов присваивает уникальные идентификаторы этих узлов, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее число узлов процессора в системе.  
  
 Количество узлов, которые могут быть получены из функции [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="a-namegetnexta--itopologynodegetnext-method"></a><a name="getnext"></a>Метод ITopologyNode::GetNext  
 Возвращает интерфейс следующего узла топологии в порядке перечисления.  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Интерфейс следующего узла в порядке перечисления. Если в порядке перечисления топологии системы больше нет узлов, этот метод возвращает значение `NULL`.  
  
##  <a name="a-namegetnumanodea--itopologynodegetnumanode-method"></a><a name="getnumanode"></a>Метод ITopologyNode::GetNumaNode  
 Возвращает Windows назначенный номер узла NUMA, к которому принадлежит данный узел которые ресурсов.  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Windows назначенный номер узла NUMA, к которому принадлежит данный узел диспетчера ресурсов.  
  
### <a name="remarks"></a>Примечания  
 Прокси потоков, выполняющихся на корневой виртуальный процессор, принадлежащие этому узлу будет иметь по крайней мере соответствие уровень узла NUMA для узла NUMA, возвращаемый этим методом.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

