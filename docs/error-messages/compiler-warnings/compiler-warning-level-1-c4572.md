---
title: Предупреждение компилятора (уровень 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: 4a1931032f6d1f8db0679dd782ff2f0ce7ff428c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162209"
---
# <a name="compiler-warning-level-1-c4572"></a>Предупреждение компилятора (уровень 1) C4572

Атрибут [ParamArray] не рекомендуется использовать в параметре/CLR, используйте "..." Используйте

Использован устаревший стиль для указания списка аргументов переменной. При компиляции для CLR используйте синтаксис с многоточием вместо <xref:System.ParamArrayAttribute>. Дополнительные сведения см. в разделе [списки аргументов переменных (...)C++(/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4572.

```cpp
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```
