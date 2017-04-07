---
title: "Класс tile_barrier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 247828a6de3a5820d75623ee438810b563f04519
ms.lasthandoff: 03/17/2017

---
# <a name="tilebarrier-class"></a>Класс tile_barrier
Синхронизирует выполнение потоков, выполняющихся в группе потока (Плитка), используя `wait` методы. Только в среде выполнения можно создать экземпляр этого класса.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
class tile_barrier;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор tile_barrier](#ctor)|Инициализирует новый экземпляр класса `tile_barrier`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Ожидание](#wait)|Указывает, что все потоки в группе потока (Плитка), необходимо остановить выполнение, пока не завершены все потоки на плитке ожидания.|  
|[wait_with_all_memory_fence](#wait_with_all_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к памяти и все потоки на плитке достигнут этот вызов.|  
|[wait_with_global_memory_fence](#wait_with_global_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к глобальной памяти и все потоки на плитке достигнут этого вызова.|  
|[wait_with_tile_static_memory_fence](#wait_with_tile_static_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока все `tile_static` доступов к памяти уже выполнены и все потоки на плитке достигнут этот вызов.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tile_barrier`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  

## <a name="tile_barrier__ctor"></a>Конструктор tile_barrier  
 Инициализирует новый экземпляр класса путем копирования существующего.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
tile_barrier(  
    const tile_barrier& _Other ) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `tile_barrier` Объект, подлежащий копированию.  

## <a name="wait"></a>Ожидание 
Указывает, что все потоки в группе потока (плитки) чтобы остановить выполнение, пока не завершены все потоки на плитке ожидания.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait() const restrict(amp);  
```    

## <a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence   
Блокирует выполнение всех потоков в мозаике до достижения этого вызова всех потоков в мозаике. Это гарантирует, что все обращения к памяти являются видимыми для других потоков в мозаике потоков и были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="wait_with_global_memory_fence"></a>wait_with_global_memory_fence   
Блокирует выполнение всех потоков в мозаике до достижения этого вызова всех потоков в мозаике. Это гарантирует, что все обращения к глобальной памяти являются видимыми для других потоков в мозаике потоков и были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="wait_with_tile_static_memory_fence"></a>wait_with_tile_static_memory_fence   
Блокирует выполнение всех потоков в мозаике до достижения этого вызова всех потоков в мозаике. Это гарантирует, что `tile_static`памяти обращается к являются видимыми для других потоков в мозаике потоков и были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

