---
title: Ошибка компилятора C2337
ms.date: 11/04/2016
f1_keywords:
- C2337
helpviewer_keywords:
- C2337
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
ms.openlocfilehash: 63f18a12ccd1962dd221324f5557c29be89eb04c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637779"
---
# <a name="compiler-error-c2337"></a>Ошибка компилятора C2337

"имя_атрибута": атрибут не найден

Используется атрибут, который не поддерживается в этой версии Visual C++.

Следующий пример приводит к возникновению ошибки C2337:

```
// C2337.cpp
// compile with: /c
[emitidl];
[module(name="x")];
[grasshopper]   // C2337, not a supported attribute
class a{};
```