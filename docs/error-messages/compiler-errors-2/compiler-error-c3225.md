---
title: Ошибка компилятора C3225 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3225
dev_langs:
- C++
helpviewer_keywords:
- C3225
ms.assetid: f5f66973-256e-4298-ac46-c87819cbde34
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d8b1251b9c13a71faf771c85924a75681deab7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033255"
---
# <a name="compiler-error-c3225"></a>Ошибка компилятора C3225

Аргумент универсального типа для «аргумент» не может быть «тип», он должен быть типом значения или тип дескриптора

Аргумент универсального типа, не соответствующего типа.

Дополнительные сведения см. в статье [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

Не удается создать экземпляр универсального типа с собственным типом. Следующий пример приводит к возникновению ошибки C3225.

```
// C3225.cpp
// compile with: /clr
class A {};

ref class B {};

generic <class T>
ref class C {};

int main() {
   C<A>^ c = gcnew C<A>;   // C3225
   C<B^>^ c2 = gcnew C<B^>;   // OK
}
```

## <a name="example"></a>Пример

В следующем примере создается компонент с помощью C#. Обратите внимание, что ограничение указывает, что универсального типа могут быть созданы только с типом значения.

```
// C3225_b.cs
// compile with: /target:library
// a C# program
public class MyList<T> where T: struct {}
```

## <a name="example"></a>Пример

Этот образец использует C#-компонент и нарушается ограничение, которое может быть только MyList экземпляр с типом значения, отличные от <xref:System.Nullable>. Следующий пример приводит к возникновению ошибки C3225.

```
// C3225_c.cpp
// compile with: /clr
#using "C3225_b.dll"
ref class A {};
value class B {};
int main() {
   MyList<A> x;   // C3225
   MyList<B> y;   // OK
}
```