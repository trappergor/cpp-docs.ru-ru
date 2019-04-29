---
title: Побочные эффекты зависимостей
ms.date: 11/04/2016
helpviewer_keywords:
- dependencies, side effects
- NMAKE program, dependents
ms.assetid: d4e8db25-fdc0-4d73-81ec-1538f2e1b3e8
ms.openlocfilehash: b89306b6e4d85e0e08729fb1d35fb041d69647e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62272117"
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

[Целевые объекты](targets.md)
