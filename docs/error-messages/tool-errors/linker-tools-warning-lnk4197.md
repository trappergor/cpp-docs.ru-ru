---
title: Предупреждение средств компоновщика LNK4197 | Документация Майкрософт
ms.custom: ''
ms.date: 09/05/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55044ce511e2584e2859b7e8a8d723cbe0976105
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894490"
---
# <a name="linker-tools-warning-lnk4197"></a>Предупреждение средств компоновщика LNK4197

> Экспорт "*exportname*" указан несколько раз; использована первая спецификация

Экспорт определено несколько и различными способами. Компоновщик использует первую спецификацию и игнорирует остальные.

Если библиотеки времени выполнения C, это сообщение можно игнорировать.

Если экспорт был указан несколько раз точно так же, компоновщик не выдаст предупреждение.

Например следующее содержимое DEF-файла приведет это предупреждение:

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Тот же Экспорт указан в командной строке (путем экспорта:) и в DEF-файле.

2. Тот же Экспорт указан дважды в DEF-файле с разными атрибутами.