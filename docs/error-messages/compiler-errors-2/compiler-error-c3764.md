---
title: Ошибка компилятора C3764 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3764
dev_langs:
- C++
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b57b9005eacc6e4a59adecc38b40027fffb5bcf1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097007"
---
# <a name="compiler-error-c3764"></a>Ошибка компилятора C3764

«переопределяющая_функция»: невозможно переопределить метод базового класса «базового класса»

Компилятор обнаружил переопределение неправильный формат. Например, функция базового класса не `virtual`. Дополнительные сведения см. в разделе [переопределить](../../windows/override-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3764.

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>Пример

C3764 также может возникнуть, когда метод базового класса — это явно и с именем переопределении. Следующий пример приводит к возникновению ошибки C3764.

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```