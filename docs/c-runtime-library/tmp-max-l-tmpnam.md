---
title: TMP_MAX, L_tmpnam
ms.date: 11/04/2016
f1_keywords:
- TMP_MAX
- L_tmpnam
helpviewer_keywords:
- temporary files, length
- L_tmpnam constant
- TMP_MAX constant
ms.assetid: ab19fd0c-b5b7-49f7-b23d-da9dfbcf0c1f
ms.openlocfilehash: 21b56a05b60067e04d0d3864a135ed5eccacfddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609720"
---
# <a name="tmpmax-ltmpnam"></a>TMP_MAX, L_tmpnam

## <a name="syntax"></a>Синтаксис

```
#include <stdio.h>
```

## <a name="remarks"></a>Примечания

`TMP_MAX` — максимальное число уникальных имен файлов, которые функция `tmpnam` может создать. `L_tmpnam` — длина имен временных файлов, создаваемых `tmpnam`.

## <a name="see-also"></a>См. также

[Глобальные константы](../c-runtime-library/global-constants.md)