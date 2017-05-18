---
title: "Структура IUMSThreadProxy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
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
ms.openlocfilehash: 46d486ddccce6f3c54627f3ea96f001e8e3bfcf7
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="iumsthreadproxy-structure"></a>Структура IUMSThreadProxy
Абстракция для потока выполнения. Если требуется предоставлять для планировщика потоки планировщика в пользовательском режиме (UMS), задайте для элемента политики планировщика `SchedulerKind` значение `UmsThreadDefault` и реализуйте интерфейс `IUMSScheduler`. Потоки UMS поддерживаются только в 64-разрядных операционных системах Windows 7 и более поздних версий.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|Вызывается для ввода критической области. Внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановках потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|Вызывается для ввода hyper критической области. Внутри гиперкритической области планировщик не будет наблюдать любые операции блокирования, происходящие во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.|  
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|Вызывается для выхода из критической области.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|Вызывается для выхода из hyper критической области.|  
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|Возвращает тип прокси-поток находится в критической области. Поскольку hyper критические области являются подмножеством критических областей, если введен код критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="entercriticalregion"></a>Метод IUMSThreadProxy::EnterCriticalRegion  
 Вызывается для ввода критической области. Внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановках потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина критической области. Критические области являются повторно входящими.  
  
##  <a name="enterhypercriticalregion"></a>Метод IUMSThreadProxy::EnterHyperCriticalRegion  
 Вызывается для ввода hyper критической области. Внутри гиперкритической области планировщик не будет наблюдать любые операции блокирования, происходящие во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина hyper критической области. Hyper критические области являются повторно входящими.  
  
### <a name="remarks"></a>Примечания  
 Планировщик должен быть чрезвычайно осторожным, какие он вызывает методы и что он блокирует получает в таких областях. Если код в такой области блокирует блокировку, которая удерживается чем-то, что планировщик планирует, может возникнуть взаимоблокировка.  
  
##  <a name="exitcriticalregion"></a>Метод IUMSThreadProxy::ExitCriticalRegion  
 Вызывается для выхода из критической области.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина критической области. Критические области являются повторно входящими.  
  
##  <a name="exithypercriticalregion"></a>Метод IUMSThreadProxy::ExitHyperCriticalRegion  
 Вызывается для выхода из hyper критической области.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина hyper критической области. Hyper критические области являются повторно входящими.  
  
##  <a name="getcriticalregiontype"></a>Метод IUMSThreadProxy::GetCriticalRegionType  
 Возвращает тип прокси-поток находится в критической области. Поскольку hyper критические области являются подмножеством критических областей, если введен код критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип критической области прокси-поток находится в пределах.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IUMSScheduler](iumsscheduler-structure.md)

