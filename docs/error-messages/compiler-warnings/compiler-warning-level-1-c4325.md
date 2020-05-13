---
title: Предупреждение компилятора (уровень 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: e0a13761b0657d054065358994638779817dad6a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163028"
---
# <a name="compiler-warning-level-1-c4325"></a>Предупреждение компилятора (уровень 1) C4325

> атрибуты для стандартного раздела "*раздел*" пропущены

## <a name="remarks"></a>Remarks

Вы не можете изменить атрибуты стандартного раздела. Пример:

```cpp
#pragma section(".sdata", long)
```

Это приведет к перезаписи `.sdata` стандартного раздела, который использует **короткий** тип данных с типом данных **Long** .

Стандартные разделы, атрибуты которых вы не можете изменить:

- . Data

- . sdata

- . BSS

- . SBSS

- .text

- . const

- . сконст

- . rdata

- . срдата

Дополнительные разделы можно добавить позже.

## <a name="see-also"></a>См. также раздел

[section](../../preprocessor/section.md)
