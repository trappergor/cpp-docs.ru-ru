---
title: -SECTION (DUMPBIN) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- -SECTION dumpbin option
- SECTION option
- /SECTION dumpbin option
- SECTION dumpbin option
ms.assetid: c223d1c6-88ef-411c-9607-c610726b8d66
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c384ef6e842213e75ec0d8a7f7e9b03b576f8d6b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721166"
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