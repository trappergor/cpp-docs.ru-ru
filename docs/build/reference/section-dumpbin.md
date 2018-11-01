---
title: /SECTION (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /section
helpviewer_keywords:
- -SECTION dumpbin option
- SECTION option
- /SECTION dumpbin option
- SECTION dumpbin option
ms.assetid: c223d1c6-88ef-411c-9607-c610726b8d66
ms.openlocfilehash: f4e36c9c651c3d89982e9145d107cc0813465dfa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676248"
---
# <a name="section-dumpbin"></a>/SECTION (DUMPBIN)

```
/SECTION:section
```

## <a name="remarks"></a>Примечания

Этот параметр ограничивает выходные данные к сведениям на указанном *разделе*. Используйте [/Headers](../../build/reference/headers.md) параметр, чтобы получить список разделов в файле.

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)