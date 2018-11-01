---
title: Класс simple_partitioner
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: f3c5792a13d9e63a05ce6710dea77828f2510f0d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522451"
---
# <a name="simplepartitioner-class"></a>Класс simple_partitioner

Класс `simple_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на фрагменты таким образом, что каждый фрагмент имеет число итераций не менее указанного размера фрагмента.

## <a name="syntax"></a>Синтаксис

```
class simple_partitioner;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[simple_partitioner](#ctor)|Создает объект `simple_partitioner`.|
|[~ simple_partitioner деструктор](#dtor)|Уничтожает объект `simple_partitioner`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`simple_partitioner`

## <a name="requirements"></a>Требования

**Заголовок:** ppl.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~ simple_partitioner

Уничтожает объект `simple_partitioner`.

```
~simple_partitioner();
```

##  <a name="ctor"></a> simple_partitioner

Создает объект `simple_partitioner`.

```
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>Параметры

*_Chunk_size*<br/>
Минимальный размер раздела.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
