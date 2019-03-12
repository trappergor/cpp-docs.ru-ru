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
ms.openlocfilehash: 680ce31065711684dcbe3077e3114ed6efec5704
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743781"
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
