---
title: __clrcall | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __clrcall_cpp
dev_langs:
- C++
helpviewer_keywords:
- __clrcall keyword [C++]
ms.assetid: 92096695-683a-40ed-bf65-0c8443572152
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9631ac9beb0e6263ac1cf7e60e11e498aa4c7667
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019761"
---
# <a name="clrcall"></a>__clrcall

**Блок, относящийся только к системам Microsoft**

Указывает, что функцию можно вызвать только из управляемого кода.  Используйте **__clrcall** для всех виртуальных функций, которые будут вызываться только из управляемого кода. Однако это соглашение о вызовах невозможно использовать для функций, которые будут вызываться из машинного кода.

Используйте **__clrcall** для повышения производительности при вызове из управляемой функции в виртуальную управляемую функцию или из управляемой функции в управляемую функцию с помощью указателя.

Точки входа представляют собой отдельные функции, создаваемые компилятором. Если функция имеет машинные и управляемые точки входа, одна из них будет фактической функцией с реализацией функции. Другая функция будет отдельной функцией (преобразователем), которая вызывает фактическую функцию и позволяет среде CLR выполнять PInvoke. Если функция отмечена как **__clrcall**, необходимо указать реализация функции должна быть MSIL и что функция машинной точки входа не создается.

При получении адреса собственной функции, если **__clrcall** не указан, компилятор использует машинную точку входа. **__clrcall** указывает, что функция является управляемой и нет необходимости выполнять преобразование из управляемой функции в собственную. В этом случае компилятор использует управляемую точку входа.

Когда `/clr` (не `/clr:pure` или `/clr:safe`) используется и **__clrcall** — не используется, при получении адреса функции всегда возвращает адрес функция машинной точки входа. Когда **__clrcall** — используется, функция машинной точки входа не создается, чтобы получить адрес управляемой функции, а не функция преобразователя точки входа. Дополнительные сведения см. в разделе [двойного](../dotnet/double-thunking-cpp.md). **/CLR: pure** и **/CLR: safe** параметры компилятора признаны устаревшими в Visual Studio 2015 и не поддерживается в Visual Studio 2017.

[/ CLR (компиляция CLR)](../build/reference/clr-common-language-runtime-compilation.md) подразумевает, что все функции и указатели функций являются **__clrcall** и компилятор не разрешает функцию в единице компиляции помечается как ничего, кроме **__clrcall**. Когда **/CLR: pure** используется, **__clrcall** можно указать только в указателях функций и во внешних объявлениях.

Можно напрямую вызвать **__clrcall** функции на основе существующего кода C++, который был скомпилирован с помощью **/CLR** до тех пор, пока функция имеет реализацию MSIL. **__clrcall** функции не может вызываться напрямую из функций, которые имеют встроенные asm и вызвать код для конкретного Процессора, например, даже если эти функции скомпилированы с `/clr`.

**__clrcall** указатели функций предназначены только для использования в домене приложения, в котором они были созданы.  Вместо передачи **__clrcall** указатели на функции между доменами приложений, используйте <xref:System.CrossAppDomainDelegate>. Дополнительные сведения см. в разделе [домены приложений и Visual C++](../dotnet/application-domains-and-visual-cpp.md).

## <a name="example"></a>Пример

Обратите внимание, что если функция объявляется с **__clrcall**, будет создаваться код, при необходимости; например, при вызове функции.

```cpp
// clrcall2.cpp
// compile with: /clr
using namespace System;
int __clrcall Func1() {
   Console::WriteLine("in Func1");
   return 0;
}

// Func1 hasn't been used at this point (code has not been generated),
// so runtime returns the adddress of a stub to the function
int (__clrcall *pf)() = &Func1;

// code calls the function, code generated at difference address
int i = pf();   // comment this line and comparison will pass

int main() {
   if (&Func1 == pf)
      Console::WriteLine("&Func1 == pf, comparison succeeds");
   else
      Console::WriteLine("&Func1 != pf, comparison fails");

   // even though comparison fails, stub and function call are correct
   pf();
   Func1();
}
```

```Output
in Func1
&Func1 != pf, comparison fails
in Func1
in Func1
```

## <a name="example"></a>Пример

В следующем примере показано, что можно определить указатель функции, например объявить, что указатель функции будет вызываться только из управляемого кода. Это позволит компилятору непосредственно вызвать управляемую функцию и избежать машинной точки входа (проблема двойного преобразования).

```cpp
// clrcall3.cpp
// compile with: /clr
void Test() {
   System::Console::WriteLine("in Test");
}

int main() {
   void (*pTest)() = &Test;
   (*pTest)();

   void (__clrcall *pTest2)() = &Test;
   (*pTest2)();
}
```

## <a name="see-also"></a>См. также

[Передача аргументов и соглашения об именовании](../cpp/argument-passing-and-naming-conventions.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
