---
title: "Структура DispatchState | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a617d1f1d7f68c00c7011daffc6ba59f08c43a1e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
|[DispatchState::DispatchState](#ctor)|Создает новый `DispatchState` объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Размер этой структуры, которая используется для управления версиями.|  
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Указывает, является ли этот контекст вошел `Dispatch` метод, так как предыдущий контекст асинхронно блокирован. Это используется только в контексте планирования UMS и присвоено значение `0` для всех контекстов выполнения.|  
|[DispatchState::m_reserved](#m_reserved)|Биты, зарезервированы для будущих передач информации.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `DispatchState`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>Конструктор DispatchState::DispatchState  
 Создает новый `DispatchState` объекта.  
  
```
DispatchState();
```  
  
##  <a name="m_dispatchstatesize"></a>Член данных Dispatchstate::m_dispatchstatesize  
 Размер этой структуры, которая используется для управления версиями.  
  
```
unsigned long m_dispatchStateSize;
```  
  
##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>Член данных Dispatchstate::m_fispreviouscontextasynchronouslyblocked  
 Указывает, является ли этот контекст вошел `Dispatch` метод, так как предыдущий контекст асинхронно блокирован. Это используется только в контексте планирования UMS и присвоено значение `0` для всех контекстов выполнения.  
  
```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```  
  
##  <a name="m_reserved"></a>Член данных Dispatchstate::m_reserved  
 Биты, зарезервированы для будущих передач информации.  
  
```
unsigned int m_reserved : 31;
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

