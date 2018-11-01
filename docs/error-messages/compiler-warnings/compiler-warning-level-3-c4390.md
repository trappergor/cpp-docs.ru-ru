---
title: Предупреждение компилятора (уровень 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 4ca00f892adc8fe3ac1bffb59a27ea1744249dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479525"
---
# <a name="compiler-warning-level-3-c4390"></a>Предупреждение компилятора (уровень 3) C4390

";": пустой контролируемый оператор найден; Это правильно?

После оператора control, не содержащего обнаружено точку с запятой.

Если вы получаете C4390 из-за макроса, следует использовать [предупреждение](../../preprocessor/warning.md) директиву pragma, чтобы отключить предупреждение C4390 в модуль, содержащий макрос.

Следующий пример приводит к возникновению ошибки C4390:

```
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```