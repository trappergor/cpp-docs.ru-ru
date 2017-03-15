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
- amp/Concurrency::tile_barrier
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 7ace6bb366881f9e5a9678b3a005f3079542c9cd
ms.lasthandoff: 02/24/2017

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
|[wait-метод](#wait)|Указывает, что все потоки в группе потока (Плитка), необходимо остановить выполнение, пока не завершены все потоки на плитке ожидания.|  
|[wait_with_all_memory_fence метод](#wait_with_all_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к памяти и все потоки на плитке достигнут этот вызов.|  
|[wait_with_global_memory_fence метод](#wait_with_global_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока не будут завершены все обращения к глобальной памяти и все потоки на плитке достигнут этого вызова.|  
|[wait_with_tile_static_memory_fence метод](#wait_with_tile_static_memory_fence)|Блокирует выполнение всех потоков в мозаике, пока все `tile_static` доступов к памяти уже выполнены и все потоки на плитке достигнут этот вызов.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `tile_barrier`  
  
## <a name="requirements"></a>Требования  
 **Заголовок** : amp.h  
  
 **Пространство имен** : Concurrency  

## <a name="a-nametilebarrierctora--tilebarrier-constructor"></a><a name="tile_barrier__ctor"></a>Конструктор tile_barrier  
 Инициализирует новый экземпляр класса путем копирования существующего.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
tile_barrier(  
    const tile_barrier& _Other ) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `tile_barrier` Объект, подлежащий копированию.  

## <a name="a-namewaita--wait"></a><a name="wait"></a>Ожидание 
Указывает, что все потоки в группе потока (плитки) чтобы остановить выполнение, пока не завершены все потоки на плитке ожидания.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait() const restrict(amp);  
```    

## <a name="a-namewaitwithallmemoryfencea--waitwithallmemoryfence"></a><a name="wait_with_all_memory_fence"></a>wait_with_all_memory_fence   
Блокирует выполнение всех потоков в мозаике до достижения этого вызова всех потоков в мозаике. Это гарантирует, что все обращения к памяти являются видимыми для других потоков в мозаике потоков и были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_all_memory_fence() const restrict(amp);  
```  
  

## <a name="a-namewaitwithglobalmemoryfencea--waitwithglobalmemoryfence"></a><a name="wait_with_global_memory_fence"></a>wait_with_global_memory_fence   
Блокирует выполнение всех потоков в мозаике до достижения этого вызова всех потоков в мозаике. Это гарантирует, что все обращения к глобальной памяти являются видимыми для других потоков в мозаике потоков и были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_global_memory_fence() const  restrict(amp);  
```

## <a name="a-namewaitwithtilestaticmemoryfencea--waitwithtilestaticmemoryfence"></a><a name="wait_with_tile_static_memory_fence"></a>wait_with_tile_static_memory_fence   
Блокирует выполнение всех потоков в мозаике до достижения этого вызова всех потоков в мозаике. Это гарантирует, что `tile_static`памяти обращается к являются видимыми для других потоков в мозаике потоков и были выполнены в порядке программы.  
  
### <a name="syntax"></a>Синтаксис 
  
```  
void wait_with_tile_static_memory_fence() const restrict(amp);  
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

