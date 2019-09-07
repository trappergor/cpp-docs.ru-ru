---
title: Предупреждение компилятора (уровень 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 10c0211bfda354a00e05cba3131d047fce843df8
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741108"
---
# <a name="compiler-warning-level-1-c4145"></a>Предупреждение компилятора (уровень 1) C4145

"выражение1": использование выражения с оператором отношения в качестве выражения для выбора вариантов; возможное смешение с "выражение2"

Оператор `switch` использует выражение отношения в качестве управляющего, результатом вычисления которого является логическое значение для операторов **case** . Вы имели в виду *выражение2*?

## <a name="example"></a>Пример

При компиляции следующего примера будет выдано предупреждение C4145:

```
// C4145.cpp
// compile with: /W1
int main() {
   int i = 0;
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve
      case 1:
         break;
      default:
         break;
   }
}
```