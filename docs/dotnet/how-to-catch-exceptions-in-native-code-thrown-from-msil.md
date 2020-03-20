---
title: Практическое руководство. Исключения в машинном коде, создаваемые MSIL
ms.date: 11/04/2016
helpviewer_keywords:
- exceptions, catching
- catching exceptions, thrown from MSIL
- MSIL, catching exceptions in native code
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
ms.openlocfilehash: 23adb573a62e93933c487f611c05aed4c08494ef
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545087"
---
# <a name="how-to-catch-exceptions-in-native-code-thrown-from-msil"></a>Практическое руководство. Исключения в машинном коде, создаваемые MSIL

В машинном коде можно перехватывать собственное C++ исключение из MSIL.  Исключения CLR можно перехватывать с помощью `__try` и `__except`.

Дополнительные сведения см. в разделе [структурированная обработка исключений (C++C/)](../cpp/structured-exception-handling-c-cpp.md) и [современные C++ рекомендации по исключениям и обработке ошибок](../cpp/errors-and-exception-handling-modern-cpp.md).

## <a name="example"></a>Пример

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

## <a name="example"></a>Пример

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

## <a name="see-also"></a>См. также:

[Обработка исключений](../extensions/exception-handling-cpp-component-extensions.md)
