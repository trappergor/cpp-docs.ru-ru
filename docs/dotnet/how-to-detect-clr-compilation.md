---
title: Практическое руководство. Обнаружение компиляции - clr
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 0b02be1bcd0afc9fd857e689ceafdcab5eaf05d1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746517"
---
# <a name="how-to-detect-clr-compilation"></a>Практическое руководство. Обнаружение компиляции/CLR

Используйте `_MANAGED` или `_M_CEE` макрос, если модуль компилируется с **/CLR**. Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md).

Дополнительные сведения о макросах см. в разделе [предустановленные макросы](../preprocessor/predefined-macros.md).

## <a name="example"></a>Пример

```
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

## <a name="see-also"></a>См. также

[Использование взаимодействия языка C++ (неявный PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
