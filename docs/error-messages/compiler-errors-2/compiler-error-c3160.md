---
title: Ошибка компилятора C3160 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3160
dev_langs:
- C++
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf3ecc18e1afc9b13e47ad8b20bb92f7686d0cfc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042277"
---
# <a name="compiler-error-c3160"></a>Ошибка компилятора C3160

pointer: данные-член управляемого класса или класса WinRT не могут иметь этот тип

Внутренние указатели сборки мусора могут указывать на внутреннюю часть управляемого класса или класса WinRT. Так как они выполняются медленнее, чем указатели на весь объект, и требуют специальной обработки сборщиком мусора, внутренние управляемые указатели нельзя объявлять как члены класса.

Следующий пример приводит к возникновению ошибки C3160:

```
// C3160.cpp
// compile with: /clr
ref struct A {
   // cannot create interior pointers inside a class
   interior_ptr<int> pg;   // C3160
   int g;   // OK
   int* pg2;   // OK
};

int main() {
   interior_ptr<int> pg2;   // OK
}
```
