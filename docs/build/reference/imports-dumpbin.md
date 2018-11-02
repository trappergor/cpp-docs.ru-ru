---
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 9367457a8e7f6be1f372244f8288a994eb777071
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613790"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Этот параметр отображает список библиотек DLL (оба статически компонуемые и [загрузка с задержкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)), которые импортируются в исполняемый файл или библиотеку DLL и все отдельные операции импорта из каждого из этих библиотек DLL.

Необязательный `file` спецификации позволяет указать, что импорты для этой библиотеки DLL будет отображаться. Пример:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Примечания

В результатах, отображаемых, этот параметр аналогичен [/EXPORTS](../../build/reference/dash-exports.md) выходных данных.

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)