---
title: Предупреждение командной строки D9027 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9027
dev_langs:
- C++
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 105ebbf62027ac3d9377c513c4f7c59e261b983d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112529"
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