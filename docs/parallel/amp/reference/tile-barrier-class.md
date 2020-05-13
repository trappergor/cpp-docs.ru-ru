---
title: Класс tile_barrier
ms.date: 03/27/2019
f1_keywords:
- tile_barrier
- AMP/tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::tile_barrier
- AMP/Concurrency::tile_barrier::tile_barrier::wait
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_all_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_global_memory_fence
- AMP/Concurrency::tile_barrier::tile_barrier::wait_with_tile_static_memory_fence
helpviewer_keywords:
- tile_barrier class
ms.assetid: b4ccdccb-0032-4e11-b7bd-dc9d43445dee
ms.openlocfilehash: c00f1e41e70e723be185959eeff176390def7647
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374725"
---
# <a name="tile_barrier-class"></a>Класс tile_barrier

Синхронизирует выполнение потоков, работающих в группе потоков (плитка) `wait` с помощью методов. Только время выполнения может мгновенно изврать этот класс.

## <a name="syntax"></a>Синтаксис

```cpp
class tile_barrier;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[tile_barrier конструктор](#ctor)|Инициализирует новый экземпляр класса `tile_barrier`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Подожди](#wait)|Инструктирует все потоки в группе потоков (плитка) прекратить выполнение до тех пор, пока все потоки в плитке не закончат ожидание.|
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Блоки выполнения всех потоков в плитке до тех пор, пока все доступы к памяти не будут завершены и все потоки в плитке не достигнут этого вызова.|
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Блоки выполнения всех потоков в плитке до тех пор, пока все глобальные доступы к памяти не будут завершены и все потоки в плитке не достигнут этого вызова.|
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Блоки выполнения всех потоков в `tile_static` плитке до тех пор, пока все доступы к памяти не будут завершены и все потоки в плитке не достигнут этого вызова.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`tile_barrier`

## <a name="requirements"></a>Требования

**Заголовок** : amp.h

**Пространство имен** : Concurrency

## <a name="tile_barrier-constructor"></a><a name="ctor"></a>tile_barrier конструктор

Инициализирует новый экземпляр класса, копируя существующий экземпляр.

### <a name="syntax"></a>Синтаксис

```cpp
tile_barrier(
    const tile_barrier& _Other ) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Копируемый объект `tile_barrier`.

## <a name="wait"></a>wait

Инструктирует все потоки в группе потоков (плитка) остановить выполнение до тех пор, пока все потоки в плитке не закончат ожидание.

### <a name="syntax"></a>Синтаксис

```cpp
void wait() const restrict(amp);
```

## <a name="wait_with_all_memory_fence"></a><a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence

Блоки выполнения всех потоков в плитке до тех пор, пока все потоки в плитке не достигнут этого вызова. Это гарантирует, что все доступы к памяти будут видны другим потокам в плитке потока и выполнены в порядке программы.

### <a name="syntax"></a>Синтаксис

```cpp
void wait_with_all_memory_fence() const restrict(amp);
```

## <a name="a-namewait_with_global_memory_fence-wait_with_global_memory_fence"></a><a name="wait_with_global_memory_fence">wait_with_global_memory_fence

Блоки выполнения всех потоков в плитке до тех пор, пока все потоки в плитке не достигнут этого вызова. Это гарантирует, что все глобальные доступы к памяти будут видны другим потокам в плитке потока и выполнены в порядке программы.

### <a name="syntax"></a>Синтаксис

```cpp
void wait_with_global_memory_fence() const  restrict(amp);
```

## <a name="a-namewait_with_tile_static_memory_fence-wait_with_tile_static_memory_fence"></a><a name="wait_with_tile_static_memory_fence">wait_with_tile_static_memory_fence

Блоки выполнения всех потоков в плитке до тех пор, пока все потоки в плитке не достигнут этого вызова. Это гарантирует, `tile_static` что доступ к памяти будет виден другим потокам в плитке потока и выполнен в порядке программы.

### <a name="syntax"></a>Синтаксис

```cpp
void wait_with_tile_static_memory_fence() const restrict(amp);
```

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
