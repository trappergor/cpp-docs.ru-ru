---
title: Предупреждение компилятора (уровень 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: b4d3356522faacfc343c33908b64597387fbe51c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521077"
---
# <a name="compiler-warning-level-1-c4572"></a>Предупреждение компилятора (уровень 1) C4572

Атрибут [ParamArray] не рекомендуется использовать с параметром/CLR, используйте «...» вместо

Использовался устаревший способ определения переменное число аргументов. При компиляции для среды CLR, используйте многоточие вместо <xref:System.ParamArrayAttribute>. Дополнительные сведения см. в разделе [списками аргументов переменных (...) (C + +/ CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4572.

```
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```