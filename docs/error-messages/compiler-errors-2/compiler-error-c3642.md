---
title: Ошибка компилятора C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: 7c3f9f05bf04c9a1c20fff7910836e7b50468a8e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742461"
---
# <a name="compiler-error-c3642"></a>Ошибка компилятора C3642

"return_type/args": невозможно вызвать функцию с __clrcallным соглашением о вызовах из машинного кода

Функция, помеченная соглашением о вызовах [__clrcall](../../cpp/clrcall.md) , не может быть вызвана из машинного (неуправляемого) кода.

*return_type/args* является либо именем функции, либо типом функции `__clrcall`, которую вы пытаетесь вызвать.  Тип используется при вызове через указатель на функцию.

Чтобы вызвать управляемую функцию из собственного контекста, можно добавить функцию-оболочку, которая будет вызывать функцию `__clrcall`. Также можно использовать механизм маршалирования среды CLR. Дополнительные сведения см. [в разделе инструкции. маршалирование указателей функций с помощью PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) .

Следующий пример приводит к возникновению ошибки C3642:

```cpp
// C3642.cpp
// compile with: /clr
using namespace System;
struct S {
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall
      Console::WriteLine(s);
   }
   void Test2(char * s) {
      Test(gcnew String(s));
   }
};

#pragma unmanaged
int main() {
   S s;
   s.Test("abc");   // C3642
   s.Test2("abc");   // OK
}
```
