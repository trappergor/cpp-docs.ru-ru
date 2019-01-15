---
title: HUGE_VAL, _HUGE
ms.date: 11/04/2016
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
ms.openlocfilehash: b1d9b099684d9671a60dd1afb1e6692e3c0d2a65
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220482"
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE

## <a name="syntax"></a>Синтаксис

```
#include <math.h>
```

## <a name="remarks"></a>Примечания

`HUGE_VAL` является максимальным представимым значением double. Это значение возвращается многими математическими функциями времени выполнения при возникновении ошибки. Для некоторых функций возвращается значение –`HUGE_VAL`. `HUGE_VAL` определяется как `_HUGE`, но математические функции времени выполнения возвращают `HUGE_VAL`. Для согласованности в коде также необходимо использовать значение `HUGE_VAL`.

## <a name="see-also"></a>См. также раздел

[Глобальные константы](../c-runtime-library/global-constants.md)
