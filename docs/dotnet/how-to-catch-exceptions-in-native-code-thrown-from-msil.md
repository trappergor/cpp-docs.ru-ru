---
title: Практическое руководство. Перехват исключений в машинном коде, создаваемых MSIL
description: Примеры перехвата исключений в машинном коде, созданном из MSIL.
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: b68a771d27e091f86331703b55bc2eb52dfbb41b
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898575"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Практическое руководство. Перехват исключений в машинном коде, создаваемых MSIL

В машинном коде можно перехватывать собственное исключение C++ из MSIL.  Исключения CLR можно перехватывать с помощью **`__try`** и **`__except`** .

Дополнительные сведения см. в разделе [структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md) и [современные рекомендации по C++ для исключений и обработки ошибок](../cpp/errors-and-exception-handling-modern-cpp.md).

## <a name="example-1"></a>Пример 1

В следующем примере определяется модуль с двумя функциями, один из которых создает собственное исключение, а другой вызывает исключение MSIL.

```cpp
// catch_MSIL_in_native.cpp
// compile with: /clr /c
void Test() {
   throw ("error");
}

void Test2() {
   throw (gcnew System::Exception("error2"));
}
```

## <a name="example-2"></a>Пример 2

В следующем примере определяется модуль, который перехватывает исключение native и MSIL.

```cpp
// catch_MSIL_in_native_2.cpp
// compile with: /clr catch_MSIL_in_native.obj
#include <iostream>
using namespace std;
void Test();
void Test2();

void Func() {
   // catch any exception from MSIL
   // should not catch Visual C++ exceptions like this
   // runtime may not destroy the object thrown
   __try {
      Test2();
   }
   __except(1) {
      cout << "caught an exception" << endl;
   }

}

int main() {
   // catch native C++ exception from MSIL
   try {
      Test();
   }
   catch(char * S) {
      cout << S << endl;
   }
   Func();
}
```

```Output
error
caught an exception
```

## <a name="see-also"></a>См. также

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)
