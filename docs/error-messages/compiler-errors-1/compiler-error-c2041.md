---
title: Ошибка компилятора C2041
ms.date: 11/04/2016
f1_keywords:
- C2041
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
ms.openlocfilehash: 7e148ced19e34a57172e3d606c6efdb2f5d012d6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740459"
---
# <a name="compiler-error-c2041"></a>Ошибка компилятора C2041

недопустимая цифра "символ" для основания "Number"

Указанный символ не является допустимой цифрой для основания (например, восьмеричной или шестнадцатеричной).

Следующий пример приводит к возникновению ошибки C2041:

```cpp
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

Возможное решение

```cpp
// C2041b.cpp
// compile with: /c
int j = 071;
```
