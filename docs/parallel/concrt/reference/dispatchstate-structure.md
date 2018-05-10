---
title: Структура DispatchState | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89d3b62248d305e6acebdc8a03b7ef48c2910b28
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="dispatchstate-structure"></a>Структура DispatchState
Структура `DispatchState` используется для передачи состояния в метод `IExecutionContext::Dispatch`. Она описывает обстоятельства, при которых метод `Dispatch` вызывается для интерфейса `IExecutionContext`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct DispatchState;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[DispatchState::DispatchState](#ctor)|Создает новое `DispatchState` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Размер этой структуры, которая используется для управления версиями.|  
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Указывает, является ли этот контекст вошел `Dispatch` метода, так как предыдущий контекст асинхронно блокирован. Это используется только в контексте планирования UMS и присвоено значение `0` для всех остальных контекстов выполнения.|  
|[DispatchState::m_reserved](#m_reserved)|Биты, зарезервированы для будущих передач информации.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `DispatchState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>  Конструктор DispatchState::DispatchState  
 Создает новое `DispatchState` объекта.  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>  Член данных DispatchState::m_dispatchStateSize  
 Размер этой структуры, которая используется для управления версиями.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  Член данных DispatchState::m_fIsPreviousContextAsynchronouslyBlocked  
 Указывает, является ли этот контекст вошел `Dispatch` метода, так как предыдущий контекст асинхронно блокирован. Это используется только в контексте планирования UMS и присвоено значение `0` для всех остальных контекстов выполнения.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>  Член данных DispatchState::m_reserved  
 Биты, зарезервированы для будущих передач информации.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
