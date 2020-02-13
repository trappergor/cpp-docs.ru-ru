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
ms.openlocfilehash: 1b4cb6a856d6da7b8eee7f9cba1ad51e375c024d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140058"
---
# <a name="itopologynode-structure"></a>Структура ITopologyNode

Интерфейс для узла топологии, как определено диспетчером ресурсов. Узел содержит один или несколько ресурсов выполнения.

## <a name="syntax"></a>Синтаксис

```cpp
struct ITopologyNode;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Итопологиноде:: Жетексекутионресаурцекаунт](#getexecutionresourcecount)|Возвращает количество ресурсов выполнения, сгруппированных в этом узле.|
|[Итопологиноде:: Жетфирстексекутионресаурце](#getfirstexecutionresource)|Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.|
|[Итопологиноде:: GetId](#getid)|Возвращает уникальный идентификатор диспетчер ресурсов для этого узла.|
|[Итопологиноде:: GetNext](#getnext)|Возвращает интерфейс следующего узла топологии в порядке перечисления.|
|[Итопологиноде:: Жетнуманоде](#getnumanode)|Возвращает назначенный Windows номер узла NUMA, к которому принадлежит данный узел Маанжер ресурса.|

## <a name="remarks"></a>Remarks

Этот интерфейс обычно используется для анализа топологии системы, наблюдаемой диспетчер ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITopologyNode`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="getexecutionresourcecount"></a>Метод Итопологиноде:: Жетексекутионресаурцекаунт

Возвращает количество ресурсов выполнения, сгруппированных в этом узле.

```cpp
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Количество ресурсов выполнения, сгруппированных в этом узле.

## <a name="getfirstexecutionresource"></a>Метод Итопологиноде:: Жетфирстексекутионресаурце

Возвращает первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.

```cpp
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Первый ресурс выполнения, сгруппированный в этом узле в порядке перечисления.

## <a name="getid"></a>Метод Итопологиноде:: GetId

Возвращает уникальный идентификатор диспетчер ресурсов для этого узла.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор диспетчер ресурсов для этого узла.

### <a name="remarks"></a>Remarks

Среда выполнения с параллелизмом представляет аппаратные потоки в системе в группах узлов процессора. Узлы обычно являются производными от топологии оборудования системы. Например, все процессоры на определенном сокете или определенном узле NUMA могут принадлежать одному и тому же узлу процессора. Диспетчер ресурсов назначает уникальные идентификаторы этим узлам, начиная с `0` до и включая `nodeCount - 1`, где `nodeCount` представляет общее число узлов процессора в системе.

Количество узлов можно получить из функции [жетпроцессорнодекаунт](concurrency-namespace-functions.md).

## <a name="getnext"></a>Метод Итопологиноде:: GetNext

Возвращает интерфейс следующего узла топологии в порядке перечисления.

```cpp
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс следующего узла в порядке перечисления. Если в порядке перечисления топологии системы больше нет узлов, этот метод возвращает значение `NULL`.

## <a name="getnumanode"></a>Метод Итопологиноде:: Жетнуманоде

Возвращает назначенный Windows номер узла NUMA, к которому принадлежит данный узел Маанжер ресурса.

```cpp
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Номер узла NUMA, назначенный Windows, к которому принадлежит этот диспетчер ресурсов узел.

### <a name="remarks"></a>Remarks

Прокси-поток, выполняющийся в корне виртуального процессора, принадлежащего этому узлу, будет иметь сходство по крайней мере на уровне узла NUMA для узла NUMA, возвращаемого этим методом.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
