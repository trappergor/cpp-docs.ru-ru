---
title: Класс tile_barrier | Документы Microsoft
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
ms.openlocfilehash: 62e81b7cab8d7e8774e6ac50c5de5f256d76b232
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686494"
---
# <a name="tilebarrier-class"></a>Класс tile_barrier
Синхронизирует выполнение потоков, выполняющихся в группы потоков (плитку) с помощью `wait` методы. Только в среде выполнения можно создать экземпляр этого класса.  
  
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
|[wait](#wait)|Указывает, что все потоки в группы потоков (плитку), необходимо остановить выполнение до завершения всех потоков в плитке ожидания.|  
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все попытки доступа к памяти и все потоки в плитке достигнут этот вызов.|  
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все попытки доступа к глобальной памяти и все потоки в плитке достигнут этого вызова.|  
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока все `tile_static` обращений к памяти будут завершены, и все потоки в плитке достигнут этот вызов.|  
  
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
 `_Other`  
 `tile_barrier` Объект, подлежащий копированию.  

## <a name="wait"></a>  Ожидание 
Указывает, что все потоки в группы потоков (плитки) для остановки выполнения до завершения всех потоков в плитке ожидания.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait() const restrict(amp);  
```    

## <a name="wait_with_all_memory_fence"></a>  wait_with_all_memory_fence   
Блокирует выполнение всех потоков в мозаике, пока все потоки в плитке достигнут этого вызова. Это гарантирует, что все попытки доступа к памяти являются видимыми для других потоков в поток плитки что были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="wait_with_global_memory_fence"></a>  wait_with_global_memory_fence   
Блокирует выполнение всех потоков в мозаике, пока все потоки в плитке достигнут этого вызова. Это гарантирует, что все попытки доступа к глобальной памяти являются видимыми для других потоков в поток плитки что были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="wait_with_tile_static_memory_fence"></a>  wait_with_tile_static_memory_fence   
Блокирует выполнение всех потоков в мозаике, пока все потоки в плитке достигнут этого вызова. Это гарантирует, что `tile_static` памяти доступов являются видимыми для других потоков в поток мозаики, а также были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
