---
title: Ошибка компилятора C2668 | Документация Майкрософт
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23bb1a6fcf64590670ede2eb6aca232a5a3b4f5c
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890002"
---
# <a name="compiler-error-c2668"></a>Ошибка компилятора C2668

«функция»: неоднозначный вызов перегруженной функции

Не удалось разрешить указанный вызов перегруженной функции. Вы можете явным образом приводить один или несколько фактических параметров.

Эта ошибка также можно получить с помощью шаблона. Если, в том же классе функции-члена регулярных и функции-члена шаблонного с такой же сигнатурой, то шаблонная идти первой. Это ограничение в текущей реализации Visual C++.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2668:

```cpp
// C2668.cpp
struct A {};
struct B : A {};
struct X {};
struct D : B, X {};

void func( X, X ){}
void func( A, B ){}
D d;
int main() {
   func( d, d );   // C2668 D has an A, B, and X
   func( (X)d, (X)d );   // OK, uses func( X, X )
}
```

## <a name="example"></a>Пример

Другой способ устранения этой ошибки — с помощью [объявление using](../../cpp/using-declaration.md):

```cpp
// C2668b.cpp
// compile with: /EHsc /c
// C2668 expected
#include <iostream>
class TypeA {
public:
   TypeA(int value) {}
};

class TypeB {
   TypeB(int intValue);
   TypeB(double dbValue);
};

class TestCase {
public:
   void AssertEqual(long expected, long actual, std::string
                    conditionExpression = "");
};

class AppTestCase : public TestCase {
public:
   // Uncomment the following line to resolve.
   // using TestCase::AssertEqual;
   void AssertEqual(const TypeA expected, const TypeA actual,
                    std::string conditionExpression = "");
   void AssertEqual(const TypeB expected, const TypeB actual,
                    std::string conditionExpression = "");
};

class MyTestCase : public AppTestCase {
   void TestSomething() {
      int actual = 0;
      AssertEqual(0, actual, "Value");
   }
};
```

## <a name="example"></a>Пример

Эта ошибка также может возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: неоднозначное преобразование в приведении константы 0.

Преобразование в приведении с использованием константы 0 является неоднозначным, так как int требует преобразования обоих долго и void *. Чтобы устранить эту ошибку, приведите 0 к точному типу параметра функции, которые он используется для преобразования не потребуется выполнить (этот код будет допустимым в версии Visual C++ в Visual Studio .NET 2003 и Visual Studio .NET).

```cpp
// C2668c.cpp
#include "stdio.h"
void f(long) {
   printf_s("in f(long)\n");
}
void f(void*) {
   printf_s("in f(void*)\n");
}
int main() {
   f((int)0);   // C2668

   // OK
   f((long)0);
   f((void*)0);
}
```

## <a name="example"></a>Пример

Эта ошибка может возникнуть, так как CRT теперь имеет float и double видов все математические функции.

```cpp
// C2668d.cpp
#include <math.h>
int main() {
   int i = 0;
   float f;
   f = cos(i);   // C2668
   f = cos((float)i);   // OK
}
```

## <a name="example"></a>Пример

Эта ошибка может возникать, поскольку pow (int, int) была удалена из math.h в CRT.

```cpp
// C2668e.cpp
#include <math.h>
int main() {
   pow(9,9);   // C2668
   pow((double)9,9);   // OK
}
```

## <a name="example"></a>Пример

Этот код выполняется успешно в Visual Studio 2015, но не в Visual Studio 2017 и более поздней версией с C2668. В Visual Studio 2015 компилятор ошибочно интерпретировал инициализацию копии списка так же, как обычную инициализацию копии. Он рассматривал только преобразование конструкторов для разрешения перегрузки.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```