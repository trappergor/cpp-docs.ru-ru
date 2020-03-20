---
title: Пошаговое руководство. обнаружение и компиляция CLR
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 42b2952e3b63023ca26c6b1f7d0ccb8871082499
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79544967"
---
# <a name="how-to-detect-clr-compilation"></a>Практическое руководство. Определение факта использования ключа /clr при компиляции

Используйте макрос `_MANAGED` или `_M_CEE`, чтобы узнать, компилируется ли модуль с **параметром/CLR**. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

Дополнительные сведения о макросах см. в разделе [предопределенные макросы](../preprocessor/predefined-macros.md).

## <a name="example"></a>Пример

```cpp
// detect_CLR_compilation.cpp
// compile with: /clr
#include <stdio.h>

int main() {
   #if (_MANAGED == 1) || (_M_CEE == 1)
      printf_s("compiling with /clr\n");
   #else
      printf_s("compiling without /clr\n");
   #endif
}
```

## <a name="see-also"></a>См. также:

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
