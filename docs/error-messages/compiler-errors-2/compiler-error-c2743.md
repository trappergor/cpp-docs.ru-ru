---
title: Ошибка компилятора C2743
ms.date: 11/04/2016
f1_keywords:
- C2743
helpviewer_keywords:
- C2743
ms.assetid: 644cd444-21d2-471d-a176-f5f52c5a0b73
ms.openlocfilehash: d679ce0df0d43772a6c32aa8e00869ac1a4a082b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759650"
---
# <a name="compiler-error-c2743"></a>Ошибка компилятора C2743

"тип": невозможно перехватывать собственный тип с деструктором __clrcall или конструктором копии

Модуль, скомпилированный с **параметром/CLR** , попытался перехватить исключение собственного типа, где деструктор типа или конструктор копий использует соглашение о вызовах `__clrcall`.

При компиляции с **параметром/CLR**обработка исключений ждет, что функции-члены в собственном типе будут [__cdecl](../../cpp/cdecl.md) , а не [__clrcall](../../cpp/clrcall.md). Собственные типы с функциями-членами, использующие соглашение о вызовах `__clrcall`, не могут быть перехвачены в модуле, скомпилированном с **параметром/CLR**.

Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2743.

```cpp
// C2743.cpp
// compile with: /clr
public struct S {
   __clrcall ~S() {}
};

public struct T {
   ~T() {}
};

int main() {
   try {}
   catch(S) {}   // C2743
   // try the following line instead
   // catch(T) {}

   try {}
   catch(S*) {}   // OK
}
```
