---
title: Предупреждение компилятора (уровень 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 28b3e49717993a3bf20c8cfec5938d698266c0f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476080"
---
# <a name="compiler-warning-level-1-c4804"></a>Предупреждение компилятора (уровень 1) C4804

«Операция»: небезопасное использование типа «bool» в операции

Это предупреждение предназначено для при использовании `bool` переменной или значения непредвиденным образом. Например, C4804 возникает при использовании операторов, таких как отрицательный унарный оператор (**-**) или оператор дополнения до единицы (`~`). Компилятор вычисляет выражение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4804:

```
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```