---
title: TZNAME_MAX
ms.date: 10/22/2018
f1_keywords:
- TZNAME_MAX
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
ms.openlocfilehash: 71e5becd39f49d86573483c5451a9a2415d84181
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750940"
---
# <a name="tznamemax"></a>TZNAME_MAX

**Устаревший**. Максимально допустимая длина строки переменной названия часового пояса. Этот макрос был определен в \<limits.h> в Visual Studio 2012 и более ранних версий. Он не определен в Visual Studio 2013 и более поздних версий. Для получения длины, требуемой для хранения имени текущего часового пояса, используйте [_get_tzname](../c-runtime-library/reference/get-tzname.md).

## <a name="syntax"></a>Синтаксис

```
#include <limits.h>
```

## <a name="see-also"></a>См. также

[Константы среды](../c-runtime-library/environmental-constants.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)<br/>
[_get_tzname](../c-runtime-library/reference/get-tzname.md)
