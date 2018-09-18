---
title: Константы действия signal | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs:
- C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f2cb8e8ca907081e85be03d7576d0252cdf20ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081322"
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