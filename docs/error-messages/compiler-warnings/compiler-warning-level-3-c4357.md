---
title: Предупреждение компилятора (уровень 3) C4357
ms.date: 11/04/2016
f1_keywords:
- C4357
helpviewer_keywords:
- C4357
ms.assetid: 9259c633-3c02-4900-b94a-2d8d366d61cd
ms.openlocfilehash: 3af2e742bde40bc3787603e32efbc34e59dcb419
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198709"
---
# <a name="compiler-warning-level-3-c4357"></a>Предупреждение компилятора (уровень 3) C4357

аргумент массива параметров в списке формальных аргументов для делегата "Del" игнорируется при создании "функция"

Атрибут `ParamArray` проигнорирован, и `function` не может вызываться с переменными аргументами.

Следующий пример приводит к возникновению ошибки C4357:

```cpp
// C4357.cpp
// compile with: /clr /W3 /c
using namespace System;
public delegate void f(int i, ... array<Object^>^ varargs);   // C4357

public delegate void g(int i, array<Object^>^ varargs);   // OK
```
