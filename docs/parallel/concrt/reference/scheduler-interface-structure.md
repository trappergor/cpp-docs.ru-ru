---
title: Структура scheduler_interface
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 36feff80cab1c5d301c009a581b869d5c2bad5e9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142148"
---
# <a name="scheduler_interface-structure"></a>Структура scheduler_interface

Интерфейс планировщика

## <a name="syntax"></a>Синтаксис

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>Члены

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[scheduler_interface:: Schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scheduler_interface`

## <a name="requirements"></a>Требования

**Заголовок:** пплинтерфаце. h

**Пространство имен:** concurrency

## <a name="schedule"></a>Метод scheduler_interface:: Schedule

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
