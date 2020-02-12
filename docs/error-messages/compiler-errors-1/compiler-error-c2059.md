---
title: Ошибка компилятора C2059
ms.date: 03/26/2019
f1_keywords:
- C2059
helpviewer_keywords:
- C2059
ms.assetid: 2be4eb39-3f37-4b32-8e8d-75835e07c78a
ms.openlocfilehash: f91eb428fcb49c81187788730128545916955790
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127664"
---
# <a name="compiler-error-c2059"></a>Ошибка компилятора C2059

Синтаксическая ошибка: "token"

Маркер привел к синтаксической ошибке.

В следующем примере создается сообщение об ошибке для строки, которая объявляет `j`.

```cpp
// C2059e.cpp
// compile with: /c
// C2143 expected
// Error caused by the incorrect use of '*'.
   int j*; // C2059
```

Чтобы определить причину ошибки, проверьте не только строку, указанную в сообщении об ошибке, но и строки над ней. Если проверка строк не дает каких либо сведений о проблеме, попробуйте закомментировать строку, указанную в сообщении об ошибке, и, возможно, несколько строк выше.

Если сообщение об ошибке возникает в символе, который сразу же следует за переменной `typedef`, убедитесь, что переменная определена в исходном коде.

C2059 возникает, когда имя символа препроцессора повторно используется в качестве идентификатора. В следующем примере компилятор видит `DIGITS.ONE` как число 1, которое недопустимо в качестве имени элемента enum:

```cpp
#define ONE 1

enum class DIGITS {
    ZERO,
    ONE // error C2059
};
```

Вы можете получить C2059, если символ равен Nothing, как это может произойти, если для компиляции используется символ **/d** **=** .

```cpp
// C2059a.cpp
// compile with: /DTEST=
#include <stdio.h>

int main() {
   #ifdef TEST
      printf_s("\nTEST defined %d", TEST);   // C2059
   #else
      printf_s("\nTEST not defined");
   #endif
}
```

Еще один случай, когда может произойти C2059, — при компиляции приложения, которое указывает структуру в аргументах по умолчанию для функции. Значение аргумента по умолчанию должно быть выражением. Список инициализаторов, например тот, который использовался для инициализации структуры, не является выражением.  Чтобы устранить эту проблему, определите конструктор для выполнения необходимой инициализации.

Следующий пример приводит к возникновению ошибки C2059:

```cpp
// C2059b.cpp
// compile with: /c
struct ag_type {
   int a;
   float b;
   // Uncomment the following line to resolve.
   // ag_type(int aa, float bb) : a(aa), b(bb) {}
};

void func(ag_type arg = {5, 7.0});   // C2059
void func(ag_type arg = ag_type(5, 7.0));   // OK
```

C2059 может возникать при неправильном приведении.

Следующий пример приводит к возникновению ошибки C2059:

```cpp
// C2059c.cpp
// compile with: /clr
using namespace System;
ref class From {};
ref class To : public From {};

int main() {
   From^ refbase = gcnew To();
   To^ refTo = safe_cast<To^>(From^);   // C2059
   To^ refTo2 = safe_cast<To^>(refbase);   // OK
}
```

C2059 также может возникнуть при попытке создать имя пространства имен, содержащее точку.

Следующий пример приводит к возникновению ошибки C2059:

```cpp
// C2059d.cpp
// compile with: /c
namespace A.B {}   // C2059

// OK
namespace A  {
   namespace B {}
}
```

C2059 может возникать, если за оператором, который может определить имя (`::`, `->`и `.`), следует ключевое слово `template`, как показано в следующем примере:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::Rebind<X>::Other AX; // error C2059
};
```

По умолчанию C++ предполагается, что `AY::Rebind` не является шаблоном. Таким образом, следующий `<` интерпретируется как знак "меньше".  Компилятор должен явно сообщить, что `Rebind` является шаблоном, чтобы он мог правильно проанализировать угловую скобку. Чтобы исправить эту ошибку, используйте ключевое слово `template` в имени зависимого типа, как показано ниже:

```cpp
template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    typedef typename AY::template Rebind<X>::Other AX; // correct
};
```
