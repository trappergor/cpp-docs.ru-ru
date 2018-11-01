---
title: Структура scheduler_interface
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 9fa51aa5bd1fdea4eb1c35488654f0b5003e2efe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612775"
---
# <a name="schedulerinterface-structure"></a>Структура scheduler_interface

Интерфейс планировщика

## <a name="syntax"></a>Синтаксис

```
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[scheduler_interface::schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scheduler_interface`

## <a name="requirements"></a>Требования

**Заголовок:** pplinterface.h

**Пространство имен:** concurrency

##  <a name="schedule"></a>  Метод scheduler_interface::Schedule

```
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
