---
title: Ошибка компилятора C2975 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53cb020dc0d456f10b7cfbae82a16b2ebe5fda6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246987"
---
# <a name="compiler-error-c2975"></a>Ошибка компилятора C2975

> "*аргумент*": недопустимый аргумент шаблона для "*типа*", требуется константное выражение времени компиляции

Аргумент шаблона не соответствует объявлению шаблона; Константное выражение должно заключаться в угловые скобки. Переменные не разрешены в качестве фактических аргументов шаблона. Проверьте определение шаблона, чтобы найти правильные типы.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2975 и также показано правильное использование:

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

C2975 также возникает при использовании &#95; &#95;строки&#95; &#95; как константы времени компиляции с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md). Одним из решений будет компилироваться в [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) вместо **/ZI**.

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