---
title: Ошибка компилятора C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 25023277258d33ab77bde18f6cdfabc862f50a63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741746"
---
# <a name="compiler-error-c3821"></a>Ошибка компилятора C3821

"функция": управляемый тип или функция не могут использоваться в неуправляемой функции

Функции со встроенной сборкой или [setjmp](../../c-runtime-library/reference/setjmp.md) не могут содержать типы значений или управляемые классы. Чтобы устранить эту ошибку, удалите встроенную сборку и `setjmp` или удалите управляемые объекты.

C3821 также может возникать при попытке использовать автоматическое хранилище в функции vararg.  Дополнительные сведения см. в разделе [списки аргументов переменных (...)C++(/CLI)](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md) и [ C++ Семантика стека для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3821.

```cpp
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3821.

```cpp
// C3821b.cpp
// compile with: /clr
// processor: /x86
ref class A {
   public:
   int i;
};

int main() {
   // cannot use managed classes in this function
   A ^a;

   __asm {
      nop
   }
} // C3821
```
