---
title: Предупреждение компилятора (уровень 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 4ca00f892adc8fe3ac1bffb59a27ea1744249dea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401986"
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