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
ms.openlocfilehash: c8b0f88b38eb657fe4d3916ef0df13972e985cbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291847"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

Этот параметр отображает список библиотек DLL (оба статически компонуемые и [загрузка с задержкой](linker-support-for-delay-loaded-dlls.md)), которые импортируются в исполняемый файл или библиотеку DLL и все отдельные операции импорта из каждого из этих библиотек DLL.

Необязательный `file` спецификации позволяет указать, что импорты для этой библиотеки DLL будет отображаться. Пример:

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>Примечания

В результатах, отображаемых, этот параметр аналогичен [/EXPORTS](dash-exports.md) выходных данных.

Только [/Headers](headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
