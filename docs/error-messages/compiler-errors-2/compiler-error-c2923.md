---
title: Ошибка компилятора C2923
ms.date: 11/04/2016
f1_keywords:
- C2923
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
ms.openlocfilehash: 3046d7009d2a54bab6d4d9acf0706335ae9d1974
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761010"
---
# <a name="compiler-error-c2923"></a>Ошибка компилятора C2923

"тип": "идентификатор" не является допустимым аргументом типа шаблона для параметра "параметр"

В списке аргументов пропущен тип, необходимый для создания экземпляра шаблона или универсального класса. Проверьте объявление шаблона или универсального класса.

Следующий пример приводит к возникновению ошибки C2923:

```cpp
// C2923.cpp
template <class T> struct TC {};
int x;
int main() {
   TC<x>* tc2;   // C2923
   TC<int>* tc2;   // OK
}
```

Ошибка C2923 также может возникнуть при использовании универсальных шаблонов.

```cpp
// C2923b.cpp
// compile with: /clr /c
generic <class T> ref struct GC {};

int x;

int main() {
   GC<x>^ gc2;   // C2923
   GC<int>^ gc2;   // OK
}
```
