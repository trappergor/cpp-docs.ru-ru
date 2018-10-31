---
title: MB_CUR_MAX | Документация Майкрософт
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- TZNAME_MAX
dev_langs:
- C++
helpviewer_keywords:
- TZNAME_MAX constant
ms.assetid: e2286cb8-751d-4557-9650-5c4b98a8f7be
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc44ff3178493132c1b8d5dc168cee6be4c5bc56
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990156"
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
