---
title: Класс static_partitioner
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: a0d06326b2ecbf3c427ae24b45751f7053778a0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500897"
---
# <a name="staticpartitioner-class"></a>Класс static_partitioner

Класс `static_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на количество блоков, соответствующее количеству работников, доступных базовому планировщику.

## <a name="syntax"></a>Синтаксис

```
class static_partitioner;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[static_partitioner](#ctor)|Создает объект `static_partitioner`.|
|[~ static_partitioner деструктор](#dtor)|Уничтожает объект `static_partitioner`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`static_partitioner`

## <a name="requirements"></a>Требования

**Заголовок:** ppl.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~ static_partitioner

Уничтожает объект `static_partitioner`.

```
~static_partitioner();
```

##  <a name="ctor"></a> static_partitioner

Создает объект `static_partitioner`.

```
static_partitioner();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
