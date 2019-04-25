---
title: Ошибка компилятора C2352
ms.date: 11/04/2016
f1_keywords:
- C2352
helpviewer_keywords:
- C2352
ms.assetid: 0efad8cb-659f-4b3e-8f6f-9f8ec44d345c
ms.openlocfilehash: 387738faa5b55e60cbb9df2185efcb94098011d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388804"
---
# <a name="compiler-error-c2352"></a>Ошибка компилятора C2352

class::function: недопустимый вызов нестатической функции-члена

Функция-член `static` вызвала нестатическую функцию-член. Или нестатическая функция-член была вызвана извне класса в качестве статической функции.

В следующем примере показано возникновение ошибки C2352 и приводятся сведения по ее устранению.

```
// C2352.cpp
// compile with: /c
class CMyClass {
public:
   static void func1();
   void func2();
   static void func3() {
      func2();   // C2352 calls nonstatic func2
      func1();   // OK calls static func1
   }
};
```

В следующем примере показано возникновение ошибки C2352 и приводятся сведения по ее устранению.

```
// C2352b.cpp
class MyClass {
public:
   void MyFunc() {}
   static void MyFunc2() {}
};

int main() {
   MyClass::MyFunc();   // C2352
   MyClass::MyFunc2();   // OK
}
```