---
title: "Структура DispatchState | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::DispatchState
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 46c2219464e57da4931596e970199549405d02ec
ms.lasthandoff: 02/24/2017

---
# <a name="dispatchstate-structure"></a>Структура DispatchState
Структура `DispatchState` используется для передачи состояния в метод `IExecutionContext::Dispatch`. Она описывает обстоятельства, при которых метод `Dispatch` вызывается для интерфейса `IExecutionContext`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор DispatchState::DispatchState](#ctor)|Создает новый `DispatchState` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Член данных Dispatchstate::m_dispatchstatesize](#m_dispatchstatesize)|Размер этой структуры, которая используется для управления версиями.|  
|[Член данных Dispatchstate::m_fispreviouscontextasynchronouslyblocked](#m_fispreviouscontextasynchronouslyblocked)|Указывает, является ли этот контекст вошел `Dispatch` метод, так как предыдущий контекст асинхронно блокирован. Это используется только в контексте планирования UMS и присвоено значение `0` для всех контекстов выполнения.|  
|[Член данных Dispatchstate::m_reserved](#m_reserved)|Биты, зарезервированы для будущих передач информации.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `DispatchState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora--dispatchstatedispatchstate-constructor"></a><a name="ctor"></a>Конструктор DispatchState::DispatchState  
 Создает новый `DispatchState` объекта.  
  
```
DispatchState();
```  
  
##  <a name="a-namemdispatchstatesizea--dispatchstatemdispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a>Член данных Dispatchstate::m_dispatchstatesize  
 Размер этой структуры, которая используется для управления версиями.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="a-namemfispreviouscontextasynchronouslyblockeda--dispatchstatemfispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a>Член данных Dispatchstate::m_fispreviouscontextasynchronouslyblocked  
 Указывает, является ли этот контекст вошел `Dispatch` метод, так как предыдущий контекст асинхронно блокирован. Это используется только в контексте планирования UMS и присвоено значение `0` для всех контекстов выполнения.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="a-namemreserveda--dispatchstatemreserved-data-member"></a><a name="m_reserved"></a>Член данных Dispatchstate::m_reserved  
 Биты, зарезервированы для будущих передач информации.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

