---
title: Структура ITopologyExecutionResource
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: 82193a9b592cded96f3726cbabd6cf646eaa27c8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140067"
---
# <a name="itopologyexecutionresource-structure"></a>Структура ITopologyExecutionResource

Интерфейс для ресурса выполнения, как определено диспетчером ресурсов.

## <a name="syntax"></a>Синтаксис

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[ITopologyExecutionResource:: GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.|
|[ITopologyExecutionResource:: GetNext](#getnext)|Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.|

## <a name="remarks"></a>Remarks

Этот интерфейс обычно используется для анализа топологии системы, наблюдаемой диспетчер ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITopologyExecutionResource`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="getid"></a>Метод ITopologyExecutionResource:: GetId

Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.

## <a name="getnext"></a>Метод ITopologyExecutionResource:: GetNext

Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс для следующего ресурса выполнения в порядке перечисления. Если больше нет узлов в порядке перечисления узла, которому принадлежит этот ресурс выполнения, этот метод возвращает значение `NULL`.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
