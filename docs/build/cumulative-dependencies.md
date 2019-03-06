---
title: Кумулятивные зависимости
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: 7ac1e164d1edc8d0aec26e268b3013c5b760672b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416882"
---
# <a name="cumulative-dependencies"></a>Кумулятивные зависимости

Зависимости являются кумулятивными в блоке описания, если целевой объект повторяется.

Например это набор правил,

```Output
bounce.exe : jump.obj
bounce.exe : up.obj
   echo Building bounce.exe...
```

вычисляется как это:

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Несколько целевых объектов в нескольких строках зависимостей одного блока описания оцениваются как в том случае, если каждый объект был указан в отдельном блоке описания, но цели, которые не входят в последней строке зависимость не используйте в блоке команд. NMAKE пытается использовать правило зависимости для таких целевых показателей.

Например это набор правил,

```Output
leap.exe bounce.exe : jump.obj
bounce.exe climb.exe : up.obj
   echo Building bounce.exe...
```

вычисляется как это:

```Output

leap.exe : jump.obj
# invokes an inference rule
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
climb.exe : up.obj
   echo Building bounce.exe...
```

## <a name="see-also"></a>См. также

[Целевые объекты](../build/targets.md)
