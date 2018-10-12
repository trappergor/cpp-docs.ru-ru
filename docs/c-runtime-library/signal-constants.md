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
ms.openlocfilehash: defd5f630f1d3832014e2cc7e9746c0e00e8d816
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070669"
---
# <a name="signal-constants"></a>Константы signal

## <a name="syntax"></a>Синтаксис

```
#include <signal.h>
```

## <a name="remarks"></a>Примечания

Аргумент `sig` должен представлять собой одну из констант манифеста, определенных в SIGNAL.H (перечислены ниже).

|||
|-|-|
|SIGABRT|Аварийное завершение. По умолчанию завершает вызывающую программу с кодом выхода 3.  |
|SIGABRT_COMPAT|Аналогично SIGABRT. Для обеспечения совместимости с другими платформами.  |
|SIGFPE|Ошибка операций с плавающей запятой, например переполнение, деление на ноль или недопустимая операция. По умолчанию завершает вызывающую программу.  |
|SIGILL|Недопустимая инструкция. По умолчанию завершает вызывающую программу.  |
|SIGINT|Прерывание CTRL+C. По умолчанию завершает вызывающую программу с кодом выхода 3.  |
|SIGSEGV|Недопустимое обращение к хранилищу. По умолчанию завершает вызывающую программу.  |
|SIGTERM|В программу направлен запрос на прекращение. По умолчанию завершает вызывающую программу с кодом выхода 3.  |
|SIG_ERR|Тип значения, возвращаемого из signal с информацией о произошедшей ошибке.  |

## <a name="see-also"></a>См. также

[signal](../c-runtime-library/reference/signal.md)<br/>
[raise](../c-runtime-library/reference/raise.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)