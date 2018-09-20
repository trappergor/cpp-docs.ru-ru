---
title: Структура ITopologyExecutionResource | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
dev_langs:
- C++
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60a0097aded73e3e0251d38daf5da71197668d3a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383796"
---
# <a name="itopologyexecutionresource-structure"></a>Структура ITopologyExecutionResource

Интерфейс для ресурса выполнения, как определено диспетчером ресурсов.

## <a name="syntax"></a>Синтаксис

```
struct ITopologyExecutionResource;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[ITopologyExecutionResource::GetId](#getid)|Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.|
|[ITopologyExecutionResource::GetNext](#getnext)|Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.|

## <a name="remarks"></a>Примечания

Этот интерфейс обычно используется для обхода топологии системы, что наблюдается диспетчером ресурсов.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ITopologyExecutionResource`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="getid"></a>  Метод ITopologyExecutionResource::GetId

Возвращает уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Уникальный идентификатор диспетчера ресурсов для данного ресурса выполнения.

##  <a name="getnext"></a>  Метод ITopologyExecutionResource::GetNext

Возвращает интерфейс для следующего ресурса выполнения в порядке перечисления.

```
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Интерфейс для следующего ресурса выполнения в порядке перечисления. Если больше нет узлов в порядке перечисления узла, которому принадлежит этот ресурс выполнения, этот метод возвращает значение `NULL`.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
