---
title: Предупреждение командной строки D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 46ed5750bd1f315f20658ace9b83fac532fbbabb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196682"
---
# <a name="command-line-warning-d9027"></a>Предупреждение командной строки D9027

исходный файл "\<имя файла >" проигнорирован

Программа CL. exe проигнорировала входной исходный файл.

Это предупреждение может быть вызвано пробелом между параметром/FO и выходным именем в командной строке с параметром/c. Пример:

```
cl /c /Fo output.obj input.c
```

Поскольку между/FO и `output.obj`существует пробел, программа CL. exe принимает `output.obj` в качестве имени входного файла. Чтобы устранить эту проблему, удалите пробел:

```
cl /c /Fooutput.obj input.c
```
