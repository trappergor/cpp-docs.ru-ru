---
title: Класс affinity_partitioner
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: dac25755c388e5297ce671da09b7938f09f1ef03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337665"
---
# <a name="affinitypartitioner-class"></a>Класс affinity_partitioner

Класс `affinity_partitioner` аналогичен классу `static_partitioner`, но он повышает сходство кэша путем подбора поддиапазонов сопоставления для потоков рабочего процесса. Он может значительно повысить производительность, если цикл повторно выполняется в одном и том же наборе данных и данные помещаются в кэш. Обратите внимание, что один и тот же объект `affinity_partitioner` должен использоваться с последующими итерациями параллельного цикла, выполняемого в указанном наборе данных, чтобы воспользоваться преимуществом локальности данных.

## <a name="syntax"></a>Синтаксис

```
class affinity_partitioner;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[affinity_partitioner](#ctor)|Создает объект `affinity_partitioner`.|
|[~ affinity_partitioner деструктор](#dtor)|Уничтожает `affinity_partitioner` объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`affinity_partitioner`

## <a name="requirements"></a>Требования

**Заголовок:** ppl.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~affinity_partitioner

Уничтожает `affinity_partitioner` объекта.

```
~affinity_partitioner();
```

##  <a name="ctor"></a> affinity_partitioner

Создает объект `affinity_partitioner`.

```
affinity_partitioner();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
