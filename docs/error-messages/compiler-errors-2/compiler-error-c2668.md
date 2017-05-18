---
title: "Ошибка компилятора C2668 | Документы Microsoft"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2668
dev_langs:
- C++
helpviewer_keywords:
- C2668
ms.assetid: 041e9627-1c76-420e-a653-cfc83f933bd3
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: 6bb1dc7c1dbf26a4ff8ec25a46fe7128e0fb6aa8
ms.contentlocale: ru-ru
ms.lasthandoff: 03/29/2017

---
# <a name="compiler-error-c2668"></a>Ошибка компилятора C2668
«функция»: неоднозначный вызов перегруженной функции  
  
 Не удалось разрешить указанный вызов перегруженной функции. Можно явно укажите один или несколько фактических параметров.  
  
 Эта ошибка также можно получить с помощью шаблона. Если в том же классе имеется обычная функция-член и функции-члена шаблонного с такой же сигнатурой, то шаблонная идти первой. Это ограничение текущей реализации Visual C++.  
  
 В статье базы знаний Q240869 подробнее на частичное Упорядочение шаблонов функций.  
  
 Если вы создаете проект ATL, содержащий вспомогательного объекта COM `ISupportErrorInfo`, см. в статье базы знаний Q243298.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2668:  
  
```  
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
 Другой способ устранения этой ошибки — с [объявление using](../../cpp/using-declaration.md):  
  
```  
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
 Эта ошибка может также возникать в результате действий по обеспечению совместимости компилятора с Visual Studio .NET 2003: неоднозначное преобразование в приведении константы 0.  
  
 Преобразование в приведении с использованием константы 0 является неоднозначным, поскольку int требует преобразования как долго и void *. Чтобы устранить эту ошибку, приведите 0 к точному типу параметра функции, он используется для, чтобы никакие преобразования не выполняются (этот код будет допустим в версиях Visual C++ для Visual Studio .NET 2003 и Visual Studio .NET).  
  
```  
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
 Эта ошибка может возникать из-за CRT теперь имеет float и double форм все математические функции.  
  
```  
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
 Эта ошибка может возникать, поскольку функция pow (int, int) была удалена из math.h в CRT.  
  
```  
// C2668e.cpp  
#include <math.h>  
int main() {  
   pow(9,9);   // C2668  
   pow((double)9,9);   // OK  
}  
```

## <a name="example"></a>Пример  
Этот код выполняется успешно, в Visual Studio 2015, но завершается сбоем в Visual Studio 2017 г. и позже с помощью C2668. В Visual Studio 2015 компилятор ошибочно интерпретировал инициализацию копии списка так же, как обычную инициализацию копии. Он рассматривал только преобразование конструкторов для разрешения перегрузки. 

```
C++
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
