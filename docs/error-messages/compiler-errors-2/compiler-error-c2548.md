---
title: Ошибка компилятора C2548
ms.date: 11/04/2016
f1_keywords:
- C2548
helpviewer_keywords:
- C2548
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
ms.openlocfilehash: 2c680d86a0ea69d67f9e53a481f2f096f4cc7878
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659606"
---
# <a name="compiler-error-c2548"></a>Ошибка компилятора C2548

«класс::член»: отсутствующий параметр по умолчанию для параметра параметр

Список параметров по умолчанию отсутствует параметр. Если указан параметр по умолчанию в любом месте в списке параметров, необходимо определить параметры по умолчанию для всех последующих параметров.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2548:

```
// C2548.cpp
// compile with: /c
void func( int = 1, int, int = 3);  // C2548

// OK
void func2( int, int, int = 3);
void func3( int, int = 2, int = 3);
```