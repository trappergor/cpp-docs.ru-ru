---
title: Константы signal | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SIGTERM
- SIGFPE
- SIGABRT
- SIGILL
- SIGINT
- SIGSEGV
dev_langs:
- C++
helpviewer_keywords:
- SIGTERM constant
- SIGABRT constant
- SIGSEGV constant
- SIGFPE constant
- SIGINT constant
- signal constants
- SIGILL constant
ms.assetid: a3b39281-dae7-4e44-8d68-e6a610c669dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 279f4beb3b550f672ac3950c31f3653ca1f00ba2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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