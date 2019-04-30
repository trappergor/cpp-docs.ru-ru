---
title: Структура ITopologyNode
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 867e0543d1b9f2810a3fe761f038947c4d88da4d
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346222"
---
# <a name="itopologynode-structure"></a>Структура ITopologyNode

Интерфейс для узла топологии, как определено диспетчером ресурсов. Узел содержит один или несколько ресурсов выполнения.

## <a name="syntax"></a>Синтаксис

```
struct ITopologyNode;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|Возвращает количество ресурсов выполнения, сгруппированных в этом узле.|
|[ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.|
|[ITopologyNode::GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для этого узла.|
|[ITopologyNode::GetNext](#getnext)|Возвращает интерфейс следующего узла топологии в порядке перечисления.|
|[ITopologyNode::GetNumaNode](#getnumanode)|Возвращает Windows назначается номер узла NUMA, к которому принадлежит данный узел которые ресурсов.|

## <a name="remarks"></a>Примечания

Этот интерфейс обычно используется для обхода топологии системы, что наблюдается диспетчером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITopologyNode`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="getexecutionresourcecount"></a>  Метод ITopologyNode::GetExecutionResourceCount

Возвращает количество ресурсов выполнения, сгруппированных в этом узле.

```
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество ресурсов выполнения, сгруппированных в этом узле.

##  <a name="getfirstexecutionresource"></a>  Метод ITopologyNode::GetFirstExecutionResource

Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.

```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.

##  <a name="getid"></a>  Метод ITopologyNode::GetId

Возвращает уникальный идентификатор диспетчера ресурсов для этого узла.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор диспетчера ресурсов для этого узла.

### <a name="remarks"></a>Примечания

Среда выполнения с параллелизмом представляет аппаратных потоков в системе в группах узлов процессора. Узлы обычно являются производными от топологии оборудования системы. Например все процессоры на определенном сокете или определенный узел NUMA могут входить в одном узле процессора. Диспетчер ресурсов назначает уникальные идентификаторы для этих узлов, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее количество узлов процессора в системе.

Количество узлов может быть получен из функции [GetProcessorNodeCount](concurrency-namespace-functions.md).

##  <a name="getnext"></a>  Метод ITopologyNode::GetNext

Возвращает интерфейс следующего узла топологии в порядке перечисления.

```
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс следующего узла в порядке перечисления. Если в порядке перечисления топологии системы больше нет узлов, этот метод возвращает значение `NULL`.

##  <a name="getnumanode"></a>  Метод ITopologyNode::GetNumaNode

Возвращает Windows назначается номер узла NUMA, к которому принадлежит данный узел которые ресурсов.

```
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Windows назначается номер узла NUMA, к которому принадлежит данный узел диспетчера ресурсов.

### <a name="remarks"></a>Примечания

Прокси потоков, выполняющихся на корневом виртуальном процессоре, принадлежащих этому узлу будет иметь соответствия по крайней мере уровень узла NUMA в узле NUMA, возвращаемого этим методом.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
