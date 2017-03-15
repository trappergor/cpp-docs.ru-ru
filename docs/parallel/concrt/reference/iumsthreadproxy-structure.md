---
title: "Структура IUMSThreadProxy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSThreadProxy
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
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 55ed05f137775e819c81ce231cf8c8ad3a9974f3
ms.lasthandoff: 02/24/2017

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
|[Метод IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|Вызывается для ввода критической области. Внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановках потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.|  
|[Метод IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|Вызывается для ввода hyper критической области. Внутри гиперкритической области планировщик не будет наблюдать любые операции блокирования, происходящие во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.|  
|[Метод IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|Вызывается для выхода из критической области.|  
|[Метод IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|Вызывается для выхода из hyper критической области.|  
|[Метод IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|Возвращает тип прокси-поток находится в критической области. Поскольку hyper критические области являются подмножеством критических областей, если введен код критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameentercriticalregiona--iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>Метод IUMSThreadProxy::EnterCriticalRegion  
 Вызывается для ввода критической области. Внутри критической области планировщик не будет наблюдать асинхронные операции блокирования, происходящие во время области. Это означает, что планировщик не будет введен к снова для ошибок страниц, приостановках потока, вызовов асинхронных процедур ядра (APC) и т. д., для потока UMS.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина критической области. Критические области являются повторно входящими.  
  
##  <a name="a-nameenterhypercriticalregiona--iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>Метод IUMSThreadProxy::EnterHyperCriticalRegion  
 Вызывается для ввода hyper критической области. Внутри гиперкритической области планировщик не будет наблюдать любые операции блокирования, происходящие во время области. Это означает, что в планировщик не будет повторных входов для блокирующих вызовов функции, блокирующих попыток получения блокировки, сбоев страниц, приостановок потока, вызовов асинхронных процедур ядра (APC) и т. п. для потока UMS.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина hyper критической области. Hyper критические области являются повторно входящими.  
  
### <a name="remarks"></a>Примечания  
 Планировщик должен быть чрезвычайно осторожным, какие он вызывает методы и что он блокирует получает в таких областях. Если код в такой области блокирует блокировку, которая удерживается чем-то, что планировщик планирует, может возникнуть взаимоблокировка.  
  
##  <a name="a-nameexitcriticalregiona--iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>Метод IUMSThreadProxy::ExitCriticalRegion  
 Вызывается для выхода из критической области.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина критической области. Критические области являются повторно входящими.  
  
##  <a name="a-nameexithypercriticalregiona--iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>Метод IUMSThreadProxy::ExitHyperCriticalRegion  
 Вызывается для выхода из hyper критической области.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новая глубина hyper критической области. Hyper критические области являются повторно входящими.  
  
##  <a name="a-namegetcriticalregiontypea--iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>Метод IUMSThreadProxy::GetCriticalRegionType  
 Возвращает тип прокси-поток находится в критической области. Поскольку hyper критические области являются подмножеством критических областей, если введен код критической области, а затем hyper критической области, `InsideHyperCriticalRegion` будут возвращены.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Тип критической области прокси-поток находится в пределах.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IUMSScheduler](iumsscheduler-structure.md)

