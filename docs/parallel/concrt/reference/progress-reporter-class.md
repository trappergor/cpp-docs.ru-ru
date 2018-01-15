---
title: "Класс progress_reporter | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs: C++
helpviewer_keywords: progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1dcdba2e5242dcd750eea42b61575ebea921d7b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="progressreporter-class"></a>Класс progress_reporter
Класс формирования отчетов о ходе выполнения позволяет формировать уведомления о ходе выполнения определенного типа. Каждый объект progress_reporter привязан к конкретному асинхронному действию или операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename _ProgressType>
class progress_reporter;
```  
  
#### <a name="parameters"></a>Параметры  
 `_ProgressType`  
 О типе полезных данных каждого уведомления о ходе выполнения сообщается посредством формирования отчетов о ходе выполнения.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[progress_reporter](#ctor)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[отчет](#report)|Отправляет отчет о ходе выполнения в асинхронное действие или операцию, к которому привязано это средство формирования отчетов.|  
  
## <a name="remarks"></a>Примечания  
 Этот тип доступен только в приложениях Магазина Windows.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `progress_reporter`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppltasks.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a>отчет 

 Отправляет отчет о ходе выполнения в асинхронное действие или операцию, к которому привязано это средство формирования отчетов.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Полезные данные в отчете с помощью уведомления о ходе выполнения.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
