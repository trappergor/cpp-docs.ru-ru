---
title: Ошибка компилятора C2040
ms.date: 11/04/2016
f1_keywords:
- C2040
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
ms.openlocfilehash: b45ec25f1ed516ae73b242fdcc7c66f68c92f724
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624722"
---
# <a name="compiler-error-c2040"></a>Ошибка компилятора C2040

operator: identifier1 отличается по уровням косвенного обращения от identifier2

Выражение, включающее заданные операнды, содержит несовместимые или неявно преобразованные типы операндов. Если оба операнда арифметические или неарифметические (например, массив или указатель), они используются без изменения. Если один из операндов арифметический, а другой — нет, арифметический операнд преобразуется в неарифметический.

В этом примере показано возникновение ошибки C2040 и приводятся сведения по ее устранению.

```
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```