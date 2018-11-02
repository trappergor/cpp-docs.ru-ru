---
title: Ошибка компилятора C2041
ms.date: 11/04/2016
f1_keywords:
- C2041
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
ms.openlocfilehash: 37d32285f9c01efb981c5f02acba21f2d6fe3dc2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593509"
---
# <a name="compiler-error-c2041"></a>Ошибка компилятора C2041

Недопустимая цифра «character» для основания «число»

Указанный символ не является допустимой цифрой для основания (например, восьмеричной или hex).

Следующий пример приводит к возникновению ошибки C2041:

```
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

Возможное решение

```
// C2041b.cpp
// compile with: /c
int j = 071;
```