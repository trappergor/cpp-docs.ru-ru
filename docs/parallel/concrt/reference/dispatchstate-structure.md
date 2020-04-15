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
ms.openlocfilehash: 2c4103f89f7fc74c5368bafac3c82685ff9b6e03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372697"
---
# <a name="dispatchstate-structure"></a>Структура DispatchState

Структура `DispatchState` используется для передачи состояния в метод `IExecutionContext::Dispatch`. Она описывает обстоятельства, при которых метод `Dispatch` вызывается для интерфейса `IExecutionContext`.

## <a name="syntax"></a>Синтаксис

```cpp
struct DispatchState;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Диспетчер::DispatchState](#ctor)|Создает новый объект `DispatchState`.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Диспетчер::m_dispatchStateSize](#m_dispatchstatesize)|Размер этой структуры, которая используется для версий.|
|[Диспетчер::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Сообщает, вошел ли `Dispatch` этот контекст в метод, поскольку предыдущий контекст асинхронно заблокирован. Это используется только в контексте планирования UMS и `0` устанавливается в значении для всех других контекстов выполнения.|
|[Диспетчер::m_reserved](#m_reserved)|Биты зарезервированы для передачи информации в будущем.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DispatchState`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Название:** параллелизм

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>Диспетчер::DispatchГосударственный конструктор

Создает новый объект `DispatchState`.

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>DispatchState::m_dispatchStateSize член данных

Размер этой структуры, которая используется для версий.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>Диспетчер::m_fIsPreviousContextAsynchronouslyBlocked член данных

Сообщает, вошел ли `Dispatch` этот контекст в метод, поскольку предыдущий контекст асинхронно заблокирован. Это используется только в контексте планирования UMS и `0` устанавливается в значении для всех других контекстов выполнения.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a>Диспетчер::m_reserved член данных

Биты зарезервированы для передачи информации в будущем.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
