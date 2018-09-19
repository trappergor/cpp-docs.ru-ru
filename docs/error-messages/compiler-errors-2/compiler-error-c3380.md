---
title: Ошибка компилятора C3380 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e35c4edaf24aacbd7eb9938a1dea2c470d32caae
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062596"
---
# <a name="compiler-error-c3380"></a>Ошибка компилятора C3380

"класс": недопустимый спецификатор уровня доступа сборки — разрешены только "public" или "private"

Ключевые слова [public](../../cpp/public-cpp.md) и [private](../../cpp/private-cpp.md) , применяемые к управляемым классам или структурам, определяют возможность предоставления класса посредством метаданных сборки. К классам программы, компилируемой с использованием параметра `public` /clr `private` , могут применяться только ключевые слова [и](../../build/reference/clr-common-language-runtime-compilation.md).

`ref` И `value` ключевые слова, при использовании с [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), указывают, что управляемый класс (см. в разделе [классы и структуры](../../windows/classes-and-structs-cpp-component-extensions.md)).

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
