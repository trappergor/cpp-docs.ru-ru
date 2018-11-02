---
title: Ошибка компилятора C3821
ms.date: 11/04/2016
f1_keywords:
- C3821
helpviewer_keywords:
- C3821
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
ms.openlocfilehash: 1cfc762cc7151eb2d55f8bd681bec935aea2acd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625970"
---
# <a name="compiler-error-c3821"></a>Ошибка компилятора C3821

«функция»: управляемый тип или функция не может использоваться в неуправляемую функцию

Функций во встроенной сборке или [setjmp](../../c-runtime-library/reference/setjmp.md) не может содержать типы значений или управляемые классы. Чтобы устранить эту ошибку, удалите встроенной сборке и `setjmp` или удаления управляемых объектов.

C3821 также может возникать при попытке использования автоматического хранения в функции с переменным количеством аргументов.  Дополнительные сведения см. в разделе [списками аргументов переменных (...) (C + +/ CLI) ](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md) и [семантика стека C++ для ссылочных типов](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3821.

```
// C3821a.cpp
// compile with: /clr /c
public ref struct R {};
void test1(...) {
   R r;   // C3821
}
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3821.

```
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
