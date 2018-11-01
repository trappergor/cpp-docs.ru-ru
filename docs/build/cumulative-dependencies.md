---
title: Кумулятивные зависимости
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, cumulative
- cumulative dependencies in NMAKE
- dependencies
ms.assetid: fa6dd777-80b8-437d-87a7-aec0ed818a49
ms.openlocfilehash: c31740b830993c91568aea6d167fd3113b04fc57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460285"
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