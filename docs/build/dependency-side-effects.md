---
title: Побочные эффекты зависимостей | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a70df679434b187bc2eee4eb4aad5881db0da1c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716544"
---
# <a name="dependency-side-effects"></a>Побочные эффекты зависимостей

Если целевой объект указан в виде двоеточия (:) в двух строках зависимостей в разных расположениях, и команды отображаются после только одну из строк, NMAKE интерпретирует зависимости, как в том случае, если рядом или их комбинация. Он не вызывается правило зависимости для зависимости, никакие команды, но вместо этого предполагается, что зависимости относятся к одному блоку описания и выполняет команды, заданные с помощью других зависимостей. Например это набор правил:

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
```

вычисляется как это:

```Output
bounce.exe : jump.obj up.obj
   echo Building bounce.exe...
```

Этот эффект не происходит, если двойное двоеточие (`::`) используется. Например это набор правил:

```Output
bounce.exe :: jump.obj
   echo Building bounce.exe...

bounce.exe :: up.obj
```

вычисляется как это:

```Output
bounce.exe : jump.obj
   echo Building bounce.exe...

bounce.exe : up.obj
# invokes an inference rule
```

## <a name="see-also"></a>См. также

[Целевые объекты](../build/targets.md)