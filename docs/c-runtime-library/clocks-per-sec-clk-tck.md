---
title: CLOCKS_PER_SEC, CLK_TCK
ms.date: 11/04/2016
f1_keywords:
- CLOCKS_PER_SEC
- CLK_TCK
helpviewer_keywords:
- CLOCKS_PER_SEC
- CLK_TCK constant
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
ms.openlocfilehash: a604425809f43be238cbcc7b9148782bb937e00f
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220365"
---
# <a name="clockspersec-clktck"></a>CLOCKS_PER_SEC, CLK_TCK

## <a name="syntax"></a>Синтаксис

```
#include <time.h>
```

## <a name="remarks"></a>Примечания

Время в секундах — значение, возвращаемое функцией `clock`, разделенное на `CLOCKS_PER_SEC`. `CLK_TCK` эквивалентно, но считается устаревшим.

## <a name="see-also"></a>См. также раздел

[часы](../c-runtime-library/reference/clock.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)
