---
title: Константы _locking | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abf776ab72d692be6d573803353f35946df145ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031943"
---
# <a name="locking-constants"></a>Константы _locking

## <a name="syntax"></a>Синтаксис

```
#include <sys/locking.h>
```

## <a name="remarks"></a>Примечания

Аргумент *mode* в вызове функции `_locking` определяет, какое действие блокировки будет выполняться.

Аргумент *mode* должен быть одной из следующих констант манифеста.

|||
|-|-|
| `_LK_LOCK`  | Блокирует указанные байты. Если заблокировать байты не удается, функция попытается повторить блокировку снова через 1 секунду. Если после 10 попыток байты все равно не удается заблокировать, функция возвращает ошибку.  |
| `_LK_RLCK`  | Эквивалентно `_LK_LOCK`.  |
|`_LK_NBLCK`  | Блокирует указанные байты. Если байты не удается заблокировать, функция возвращает ошибку.  |
| `_LK_NBRLCK`  | Эквивалентно `_LK_NBLCK`.  |
| `_LK_UNLCK`  | Разблокирует указанные байты. (Байты должны быть ранее заблокированы.)  |

## <a name="see-also"></a>См. также

[_locking](../c-runtime-library/reference/locking.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)