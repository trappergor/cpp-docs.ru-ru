---
title: Класс static_partitioner | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de1b63cf24fbc84130302fcbae2cb965e8d00597
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376024"
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
