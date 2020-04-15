---
title: Структура scheduler_interface
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: da2ebc2f9c2878baefcfa792bac08f420dbbb281
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358788"
---
# <a name="scheduler_interface-structure"></a>Структура scheduler_interface

Интерфейс планировщика

## <a name="syntax"></a>Синтаксис

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[scheduler_interface::расписание](#schedule)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scheduler_interface`

## <a name="requirements"></a>Требования

**Заголовок:** pplinterface.h

**Название:** параллелизм

## <a name="scheduler_interfaceschedule-method"></a><a name="schedule"></a>scheduler_interface::метод графика

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
