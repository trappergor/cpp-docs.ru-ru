---
title: Ошибка компилятора C2977 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2977
dev_langs:
- C++
helpviewer_keywords:
- C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad1fc9acabd37ca6c1f9c71a4f8447a8def6bb62
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057864"
---
# <a name="compiler-error-c2977"></a>Ошибка компилятора C2977

"идентификатор": слишком много аргументов типа

Универсальный класс или шаблон имеет слишком много фактических аргументов. Проверьте объявление универсального класса или шаблона, чтобы определить правильное число параметров.

Следующий пример приводит к возникновению ошибки C2977:

```
// C2977.cpp
// compile with: /c
template<class T, int i>
class MyClass {};

template MyClass< int , 1, 1 >;   // C2977
template MyClass< int , 1 >;   // OK
```

Ошибка C2977 также может возникнуть при использовании универсальных шаблонов.

```
// C2977b.cpp
// compile with: /clr
// C2977 expected
generic <class T, class U>
void f(){}

generic <class T>
ref struct GC1 {};

int main() {
   // Delete the following 2 lines to resolve.
   GC1<int, char> ^ pgc1;
   f<int,int,int>();

   // OK
   GC1<int> ^ pgc1;
   f<int, int>();
}
```