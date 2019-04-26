---
title: Ошибка компилятора C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: 516690f2524d48e7abbf7546592c6346e92c3e2e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62367451"
---
# <a name="compiler-error-c3380"></a>Ошибка компилятора C3380

"класс": недопустимый спецификатор уровня доступа сборки — разрешены только "public" или "private"

Ключевые слова [public](../../cpp/public-cpp.md) и [private](../../cpp/private-cpp.md) , применяемые к управляемым классам или структурам, определяют возможность предоставления класса посредством метаданных сборки. К классам программы, компилируемой с использованием параметра `public` /clr `private` , могут применяться только ключевые слова [и](../../build/reference/clr-common-language-runtime-compilation.md).

`ref` И `value` ключевые слова, при использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), указывают, что управляемый класс (см. в разделе [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Следующий пример приводит к возникновению ошибки C3380:

```
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
