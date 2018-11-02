---
title: Предупреждение компилятора (уровень 3) C4265
ms.date: 11/04/2016
f1_keywords:
- C4265
helpviewer_keywords:
- C4265
ms.assetid: 20547159-6f30-4cc4-83aa-927884c8bb4c
ms.openlocfilehash: f06e70f88bc0a34e2feecba19da8dd9edc630230
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558357"
---
# <a name="compiler-warning-level-3-c4265"></a>Предупреждение компилятора (уровень 3) C4265

«класс»: класс имеет виртуальные функции, но деструктор не является виртуальным

Если класс имеет виртуальные функции, но невиртуальный деструктор, объектов типа могут быть не уничтожены надлежащим образом при уничтожении класса через указатель базового класса.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4265:

```
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