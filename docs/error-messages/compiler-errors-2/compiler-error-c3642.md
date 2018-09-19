---
title: Ошибка компилятора C3642 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3642
dev_langs:
- C++
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: febd6f1a9a3b4bac8bbee59cbf8c5bead93c3fb3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047724"
---
# <a name="compiler-error-c3642"></a>Ошибка компилятора C3642

«return_type/args»: невозможно вызвать функцию с соглашением вызова из машинного кода __clrcall

Функция, которая отмечена [__clrcall](../../cpp/clrcall.md) соглашение о вызовах не может вызываться из машинного (неуправляемого) кода.

*return_type/args* имя функции или тип `__clrcall` вы пытаетесь вызвать функцию.  Тип используется при вызове через указатель функции.

Чтобы вызвать управляемую функцию из собственного контекста, можно добавить функцию «оболочки», который будет вызывать `__clrcall` функции. Или можно использовать механизм маршалинга среды CLR; см. в разделе [как: маршалинг функция указатели с помощью PInvoke](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) Дополнительные сведения.

Следующий пример приводит к возникновению ошибки C3642:

```
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