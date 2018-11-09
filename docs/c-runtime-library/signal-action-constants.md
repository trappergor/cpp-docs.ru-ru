---
title: Константы действий signal
ms.date: 11/04/2016
f1_keywords:
- SIG_IGN
- SIG_DFL
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
ms.openlocfilehash: 71c2eb796680e90cd16b1798fd478506ce7aa2c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444659"
---
# <a name="signal-action-constants"></a>Константы действий signal

Действие, выполняемое при получении сигнала прерывания, зависит от значения `func`.

## <a name="syntax"></a>Синтаксис

```
#include <signal.h>
```

## <a name="remarks"></a>Примечания

Аргумент `func` должен содержать адрес функции или одну из констант манифеста, определенных в SIGNAL.H (перечислены ниже).

|||
|-|-|
| `SIG_DFL`  | Использует ответ системы по умолчанию. Если вызывающая программа использует потоковый ввод-вывод, созданные библиотекой времени выполнения буферы не очищаются.  |
| `SIG_IGN`  | Игнорирует сигнал прерывания. Это значение нельзя использовать для `SIGFPE`, так как в этом случае состояние процесса с плавающей запятой остается неопределенным.  |
| `SIG_SGE`  | Указывает, что в signal произошла ошибка.  |
| `SIG_ACK`  | Указывает, что было получено подтверждение.  |
| `SIG_ERR`  | Тип значения, возвращаемого из signal с информацией о произошедшей ошибке.  |

## <a name="see-also"></a>См. также

[signal](../c-runtime-library/reference/signal.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)