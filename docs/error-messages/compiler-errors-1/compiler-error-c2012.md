---
title: Ошибка компилятора C2012 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2012
dev_langs:
- C++
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 695576afc4daa7bff93d40ff1477dbc1a3b06363
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46111697"
---
# <a name="compiler-error-c2012"></a>Ошибка компилятора C2012

отсутствует имя после "<"

В директиве `#include` отсутствует требуемое имя файла.

Следующий пример приводит к возникновению ошибки C2012:

```
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

Возможное решение

```
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```