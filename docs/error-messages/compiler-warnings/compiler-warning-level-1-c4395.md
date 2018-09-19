---
title: Предупреждение компилятора (уровень 1) C4395 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4395
dev_langs:
- C++
helpviewer_keywords:
- C4395
ms.assetid: 8051469a-3a39-4677-80f7-1300fbffe8ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d80f4bd5e01fdcc055452a66226f6f27ae920e90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080146"
---
# <a name="compiler-warning-level-1-c4395"></a>Предупреждение компилятора (уровень 1) C4395

«функция»: функция-член будет вызываться для копии данных initonly «член»

Функция-член был вызван для [initonly (C + +/ CLI)](../../dotnet/initonly-cpp-cli.md) элемент данных.  C4395 предупреждение, что **initonly** член данных не может изменяться функцией.

Следующий пример приводит к возникновению ошибки C4395:

```
// C4395.cpp
// compile with: /W1 /clr
public value class V {
public:
   V(int data) : m_data(data) {}

   void Mutate() {
      System::Console::WriteLine("Enter Mutate: m_data = {0}", m_data);
      m_data *= 2;
      System::Console::WriteLine("Leave Mutate: m_data = {0}", m_data);
   }

   int m_data;
};

public ref class R {
public:
   static void f() {
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
      v.Mutate();   // C4395
      System::Console::WriteLine("v.m_data = {0}", v.m_data);
   }

private:
   initonly static V v = V(4);
};

int main() {
   R::f();
}
```