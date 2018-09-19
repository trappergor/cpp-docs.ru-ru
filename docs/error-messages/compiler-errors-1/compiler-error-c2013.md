---
title: Ошибка компилятора C2013 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2013
dev_langs:
- C++
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a849900f3d981de74702d972ad9f45b7f31e5619
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113361"
---
# <a name="compiler-error-c2013"></a>Ошибка компилятора C2013

отсутствует ">"

В директиве `#include` отсутствует закрывающая угловая скобка. Чтобы устранить эту ошибку, добавьте закрывающую скобку.

Следующий пример приводит к возникновению ошибки C2013:

```
// C2013.cpp
#include <stdio.h    // C2013
```

Возможное решение

```
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```