---
title: Предупреждение командной строки D9026 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9026
dev_langs:
- C++
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 07be633e56dad6c8f0b304a3c88c1b9919221d4a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079158"
---
# <a name="command-line-warning-d9026"></a>Предупреждение командной строки D9026

параметры применяются ко всей командной строке

Параметр был указан в команде, после определения имени файла. Параметр был применен к файлу, расположенному перед ним.

Например в команде

```
CL verdi.c /G5 puccini.c
```

файл VERDI.c компилируется с параметром/G5, а не по умолчанию/G4.

Это поведение отличается от некоторых предыдущих версий, в которых применяется только для тех параметров, перед именем файла, приводит к VERDI.c с помощью/G4 и PUCCINI.c компилируемого с помощью/G5.