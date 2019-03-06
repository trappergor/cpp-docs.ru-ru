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
ms.openlocfilehash: 94009670329887a0b8a35e7b8b36996a84c7faa6
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57417506"
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
