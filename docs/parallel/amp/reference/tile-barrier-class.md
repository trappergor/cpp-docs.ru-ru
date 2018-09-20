---
title: Класс tile_barrier | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
dev_langs:
- C++
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eab8fbba799c84fdc9246659b5880cdc9f266084
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406981"
---
# <a name="tilebarrier-class"></a>Класс tile_barrier

Синхронизирует выполнение потоков, работающих в группе потоков (мозаике) с помощью `wait` методы. Только среда выполнения может создать экземпляр этого класса.

### <a name="syntax"></a>Синтаксис

```
class tile_barrier;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор tile_barrier](#ctor)|Инициализирует новый экземпляр класса `tile_barrier`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[wait](#wait)|Указывает, что все потоки в группе потоков (мозаике) остановить выполнение до завершения всех потоков в плитке ожидания.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Блокирует выполнение всех потоков в плитке, пока не будут завершены все доступы к памяти и все потоки в плитке достигнут этого вызова.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Блокирует выполнение всех потоков в плитке, пока не будут завершены все доступы к памяти и все потоки в плитке достигнут этого вызова.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Блокирует выполнение всех потоков в плитке, пока все `tile_static` будет завершено обращение к памяти и все потоки в плитке достигнут этого вызова.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tile_barrier`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="tile_barrier__ctor"></a>  Конструктор tile_barrier

Инициализирует новый экземпляр класса путем копирования существующего.

### <a name="syntax"></a>Синтаксис

```
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`tile_barrier` Копируемый объект.

## <a name="wait"></a>  Подождите

Указывает, что все потоки в группе потоков (мозаике) остановить выполнение до завершения всех потоков в плитке ожидания.

### <a name="syntax"></a>Синтаксис

```
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a>  wait_with_all_memory_fence

Блокирует выполнение всех потоков в плитке, пока все потоки в мозаике достигнут этого вызова. Это гарантирует, что все доступы к памяти видимы для других потоков в плитке потоков и доступы осуществлены в программном порядке.

### <a name="syntax"></a>Синтаксис

```
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="wait_with_global_memory_fence"></a>  wait_with_global_memory_fence

Блокирует выполнение всех потоков в плитке, пока все потоки в мозаике достигнут этого вызова. Это гарантирует, что все доступы к памяти видимы для других потоков в плитке потоков и были выполнены в программном порядке.

### <a name="syntax"></a>Синтаксис

```
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="wait_with_tile_static_memory_fence"></a>  wait_with_tile_static_memory_fence

Блокирует выполнение всех потоков в плитке, пока все потоки в мозаике достигнут этого вызова. Это гарантирует, что `tile_static` памяти доступы к видимы для других потоков в плитке потоков и выполнены в программном порядке.

### <a name="syntax"></a>Синтаксис

```
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
