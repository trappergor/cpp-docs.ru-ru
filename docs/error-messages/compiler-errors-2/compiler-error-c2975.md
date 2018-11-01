---
title: Ошибка компилятора C2975
ms.date: 11/04/2016
f1_keywords:
- C2975
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
ms.openlocfilehash: 66b7c0d61cbc8141b9ed3e5f6eb329b68eb00477
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50609759"
---
# <a name="compiler-error-c2975"></a>Ошибка компилятора C2975

> "*аргумент*": недопустимый аргумент шаблона для "*тип*", требуется константное выражение времени компиляции

Аргумент шаблона не соответствует объявлению шаблона; Константное выражение появится в угловых скобках. Переменные не разрешены в качестве фактических аргументов шаблона. Проверьте определение шаблона, чтобы найти правильные типы.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2975, а также показано правильное использование:

```cpp
// C2975.cpp
template<int I>
class X {};

int main() {
   int i = 4, j = 2;
   X<i + j> x1;   // C2975
   X<6> x2;   // OK
}
```

C2975 также происходит, когда вы используете &#95; &#95;строки&#95; &#95; как константы времени компиляции с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md). Одним из решений будет компилировать с параметром [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) вместо **/ZI**.

```cpp
// C2975b.cpp
// compile with: /ZI
// processor: x86
template<long line>
void test(void) {}

int main() {
   test<__LINE__>();   // C2975
}
```