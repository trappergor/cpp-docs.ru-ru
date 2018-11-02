---
title: Предупреждение командной строки D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482606"
---
# <a name="command-line-warning-d9027"></a>Предупреждение командной строки D9027

исходный файл "\<имя_файла >" игнорируется

CL.exe учитывается файла исходных данных.

Это предупреждение может быть вызвано пробел между параметром /Fo и имя выходного файла в командной строке с параметром. Пример:

```
cl /c /Fo output.obj input.c
```

Поскольку нет пробела между /Fo и `output.obj`, принимает CL.exe `output.obj` как имя входного файла. Чтобы исправить эту проблему, удалите пространство:

```
cl /c /Fooutput.obj input.c
```