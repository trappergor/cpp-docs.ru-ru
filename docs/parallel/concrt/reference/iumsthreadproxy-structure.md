---
title: "Структура IUMSThreadProxy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
dev_langs: C++
helpviewer_keywords: IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9d9b200db84ddbf25e514e1432fa0915d5ee383
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iumsthreadproxy-structure"></a>Структура IUMSThreadProxy
Абстракция для потока выполнения. Если требуется предоставлять для планировщика потоки планировщика в пользовательском режиме (UMS), задайте для элемента политики планировщика `SchedulerKind` значение `UmsThreadDefault` и реализуйте интерфейс `IUMSScheduler`. Потоки UMS поддерживаются только в 64-разрядных операционных системах Windows 7 и более поздних версий.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|Вызывается для ввода критической области. При использовании внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|Вызывается для ввода hyper критической области. При использовании внутри hyper критической области, планировщик не будет наблюдать любые операции блокирования, происходящие во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.|  
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|Вызывается для выхода из критической области.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|Вызывается для выхода из hyper критической области.|  
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|Возвращает тип критической области, прокси-поток находится в пределах. Поскольку hyper критические области являются подмножеством для критических областей, если введено кода критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="entercriticalregion"></a>Метод IUMSThreadProxy::EnterCriticalRegion  
 Вызывается для ввода критической области. При использовании внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина критической области. Критические области являются повторных входящих вызовов.  
  
##  <a name="enterhypercriticalregion"></a>Метод IUMSThreadProxy::EnterHyperCriticalRegion  
 Вызывается для ввода hyper критической области. При использовании внутри hyper критической области, планировщик не будет наблюдать любые операции блокирования, происходящие во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина hyper критической области. Критический с точки зрения Hyper области — повторных входящих вызовов.  
  
### <a name="remarks"></a>Примечания  
 Планировщик должен быть чрезвычайно осторожным, какие методы, которые она вызывает, и что он блокирует приобретает в таких областях. Если код в такой области блокирует блокировку, которая удерживается каким-то, что планировщик отвечает за планирование, может возникнуть взаимоблокировка.  
  
##  <a name="exitcriticalregion"></a>Метод IUMSThreadProxy::ExitCriticalRegion  
 Вызывается для выхода из критической области.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина критической области. Критические области являются повторных входящих вызовов.  
  
##  <a name="exithypercriticalregion"></a>Метод IUMSThreadProxy::ExitHyperCriticalRegion  
 Вызывается для выхода из hyper критической области.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина hyper критической области. Критический с точки зрения Hyper области — повторных входящих вызовов.  
  
##  <a name="getcriticalregiontype"></a>Метод IUMSThreadProxy::GetCriticalRegionType  
 Возвращает тип критической области, прокси-поток находится в пределах. Поскольку hyper критические области являются подмножеством для критических областей, если введено кода критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип критической области прокси-поток находится в пределах.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IUMSScheduler](iumsscheduler-structure.md)
