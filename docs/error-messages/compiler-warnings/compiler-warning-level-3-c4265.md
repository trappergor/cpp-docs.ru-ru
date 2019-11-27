---
title: Предупреждение компилятора (уровень 3) C4265
ms.date: 11/04/2016
f1_keywords:
- C4265
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
ms.openlocfilehash: 8ad07e2a920ed251467c9ffd1d0fb1765557aa7e
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051709"
---
# <a name="compiler-warning-level-3-c4265"></a>Предупреждение компилятора (уровень 3) C4265

"класс": класс содержит виртуальные функции, но деструктор не является виртуальным

Если у класса есть виртуальные функции, но невиртуальный деструктор, объекты типа могут быть не уничтожены должным образом, если класс уничтожается с помощью указателя базового класса.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4265:

```cpp
// C4265.cpp
// compile with: /W3 /c
#pragma warning(default : 4265)
class B
{
public:
   virtual void vmf();

   ~B();
   // try the following line instead
   // virtual ~B();
};   // C4265

int main()
{
   B b;
}
```