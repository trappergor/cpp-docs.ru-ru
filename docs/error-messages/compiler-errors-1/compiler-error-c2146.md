---
title: Ошибка компилятора C2146
ms.date: 11/04/2016
f1_keywords:
- C2146
helpviewer_keywords:
- C2146
ms.assetid: 6bfb7de6-6723-4486-9350-c66ef88d7a64
ms.openlocfilehash: ff9dc9861643afa364db4b6364fa5e7bb33e8c8c
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742623"
---
# <a name="compiler-error-c2146"></a>Ошибка компилятора C2146

Синтаксическая ошибка: отсутствует "token" перед идентификатором "идентификатор"

`token`Вместо этого ожидается и обнаруживается компилятор `identifier` .  Возможные причины:

1. Ошибка проверки орфографии или капитализации.

1. В объявлении идентификатора отсутствует спецификатор типа.

Эта ошибка может быть вызвана типографской ошибкой. Ошибка [C2065](../../error-messages/compiler-errors-1/compiler-error-c2065.md) обычно предшествует этой ошибке.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2146.

```cpp
// C2146.cpp
class CDeclaredClass {};

class CMyClass {
   CUndeclared m_myClass;   // C2146
   CDeclaredClass m_myClass2;   // OK
};

int main() {
   int x;
   int t x;   // C2146 : missing semicolon before 'x'
}
```

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio .NET 2003: отсутствует **`typename`** ключевое слово.

Следующий пример компилируется в Visual Studio .NET 2002, но в Visual Studio .NET 2003 он завершится ошибкой:

```cpp
// C2146b.cpp
// compile with: /c
template <typename T>
struct X {
   struct Y {
      int i;
   };
   Y memFunc();
};

template <typename T>
X<T>::Y func() { }   // C2146

// OK
template <typename T>
typename X<T>::Y func() { }
```

Эта ошибка также появится в результате работы по согласованности компилятора, выполненной для Visual Studio .NET 2003: явные специализации больше не находят параметры шаблона из основного шаблона.

Использование `T` из первичного шаблона не допускается в явной специализации. Чтобы код был допустимым в Visual Studio .NET 2003 и Visual Studio .NET, замените все экземпляры параметра шаблона в специализации явно специализированным типом.

Следующий пример компилируется в Visual Studio .NET, но в Visual Studio .NET 2003 он завершится ошибкой:

```cpp
// C2146_c.cpp
// compile with: /c
template <class T>
struct S;

template <>
struct S<int> {
   T m_t;   // C2146
   int m_t2;   // OK
};
```
