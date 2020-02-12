---
title: Структура DispatchState
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 69e00893373ccca6e2ed676fbb7f5a109c49efdf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143047"
---
# <a name="dispatchstate-structure"></a>Структура DispatchState

Структура `DispatchState` используется для передачи состояния в метод `IExecutionContext::Dispatch`. Она описывает обстоятельства, при которых метод `Dispatch` вызывается для интерфейса `IExecutionContext`.

## <a name="syntax"></a>Синтаксис

```cpp
struct DispatchState;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[DispatchState::D Испатчстате](#ctor)|Создает новый объект `DispatchState`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Description|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|Размер этой структуры, которая используется для управления версиями.|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Сообщает, вошел ли этот контекст в метод `Dispatch`, поскольку предыдущий контекст асинхронно заблокирован. Он используется только в контексте планирования UMS и устанавливается в значение `0` для всех других контекстов выполнения.|
|[DispatchState:: m_reserved](#m_reserved)|Биты, зарезервированные для будущей передачи информации.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DispatchState`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm. h

**Пространство имен:** concurrency

## <a name="ctor"></a>DispatchState: конструктор:D Испатчстате

Создает новый объект `DispatchState`.

```cpp
DispatchState();
```

## <a name="m_dispatchstatesize"></a>Элемент данных DispatchState:: m_dispatchStateSize

Размер этой структуры, которая используется для управления версиями.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="m_fispreviouscontextasynchronouslyblocked"></a>Элемент данных DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked

Сообщает, вошел ли этот контекст в метод `Dispatch`, поскольку предыдущий контекст асинхронно заблокирован. Он используется только в контексте планирования UMS и устанавливается в значение `0` для всех других контекстов выполнения.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="m_reserved"></a>Элемент данных DispatchState:: m_reserved

Биты, зарезервированные для будущей передачи информации.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
