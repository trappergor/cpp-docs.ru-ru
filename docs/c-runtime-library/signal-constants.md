---
title: "Константы signal | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
dev_langs: C++
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e47e3e7bce5a41e055f251d906ec72d98c5b285
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="signal-constants"></a>Константы signal
## <a name="syntax"></a>Синтаксис  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Аргумент `sig` должен представлять собой одну из констант манифеста, определенных в SIGNAL.H (перечислены ниже).  
  
 `SIGABRT`  
 Аварийное завершение. По умолчанию завершает вызывающую программу с кодом выхода 3.  
  
 `SIGABRT_COMPAT`  
 Аналогично SIGABRT. Для обеспечения совместимости с другими платформами.  
  
 `SIGFPE`  
 Ошибка операций с плавающей запятой, например переполнение, деление на ноль или недопустимая операция. По умолчанию завершает вызывающую программу.  
  
 `SIGILL`  
 Недопустимая инструкция. По умолчанию завершает вызывающую программу.  
  
 `SIGINT`  
 Прерывание CTRL+C. По умолчанию завершает вызывающую программу с кодом выхода 3.  
  
 `SIGSEGV`  
 Недопустимое обращение к хранилищу. По умолчанию завершает вызывающую программу.  
  
 `SIGTERM`  
 В программу направлен запрос на прекращение. По умолчанию завершает вызывающую программу с кодом выхода 3.  
  
 `SIG_ERR`  
 Тип значения, возвращаемого из signal с информацией о произошедшей ошибке.  
  
## <a name="see-also"></a>См. также  
 [signal](../c-runtime-library/reference/signal.md)   
 [raise](../c-runtime-library/reference/raise.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)