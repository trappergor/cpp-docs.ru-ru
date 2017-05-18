---
title: "Класс progress_reporter | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs:
- C++
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: 11
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
ms.openlocfilehash: 98856e26c82d01433e6f8eb0d76110aff1535936
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
  
|Имя|Описание|  
|----------|-----------------|  
|[progress_reporter](#ctor)||  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
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

