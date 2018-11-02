---
title: /LINENUMBERS
ms.date: 11/04/2016
f1_keywords:
- /linenumbers
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
ms.openlocfilehash: af6e3c7c3693bd95924a86640399b15eb3378ed7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663753"
---
# <a name="linenumbers"></a>/LINENUMBERS

```
/LINENUMBERS
```

## <a name="remarks"></a>Примечания

Этот параметр отображает номера строк COFF. Номера строк существует в объектный файл, если он был скомпилирован с помощью базы данных программы (/Zi), совместимость C7 (/ Z7), или только нумерация строк (/ Zd). Исполняемый файл или библиотека DLL содержит COFF номера строк, если он был связан с создать отладочную информацию (/ DEBUG).

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)