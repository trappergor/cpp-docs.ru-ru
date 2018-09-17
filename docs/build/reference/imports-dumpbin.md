---
title: -IMPORTS (DUMPBIN) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /imports
dev_langs:
- C++
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5b3b1e3a74fea278bc142d02f793308b6b0e054
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713574"
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