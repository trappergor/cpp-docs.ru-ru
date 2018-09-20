---
title: Класс simple_partitioner | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89114c96beb49c8f843ec8a04b08802632c61ca1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401515"
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
