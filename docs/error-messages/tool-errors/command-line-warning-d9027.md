---
title: Предупреждение командной строки D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: f89e7416efe7a0069ee2dae8df921933bbe76bcf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214132"
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