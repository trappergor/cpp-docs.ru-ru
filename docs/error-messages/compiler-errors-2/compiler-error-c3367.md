---
title: Ошибка компилятора C3367
ms.date: 11/04/2016
f1_keywords:
- C3367
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
ms.openlocfilehash: f53312fa9225270ef79d50d2ad351adce790d6fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456294"
---
# <a name="compiler-error-c3367"></a>Ошибка компилятора C3367

"функция_статического_члена": невозможно использовать статическую функцию для создания несвязанного делегата

При вызове несвязанного делегата необходимо передать экземпляр объекта. Так как статическая функция-член вызывается через имя класса, с помощью функции-члена экземпляра можно создать только несвязанный делегат.

Дополнительные сведения о несвязанные делегаты, см. в разделе [как: определение и использование делегатов (C + +/ CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3367.

```cpp
// C3367.cpp
// compile with: /clr
ref struct R {
   void b() {}
   static void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::b);   // OK
   Del ^ b = gcnew Del(&R::f);   // C3367
}
```