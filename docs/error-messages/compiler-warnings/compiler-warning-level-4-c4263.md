---
title: Предупреждение компилятора (уровень 4) C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: a035646aab2589523adb9eb0b201e2d4d781632c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555289"
---
# <a name="compiler-warning-level-4-c4263"></a>Предупреждение компилятора (уровень 4) C4263

«функция»: функция-член не переопределяет ни одной функции виртуальный член базового класса

Определение функции класса имеет имя, совпадающее с именем виртуальную функцию в базовом классе, но столько же или типа аргументов. Это эффективно скрывает виртуальную функцию в базовом классе.

Это предупреждение отключено по умолчанию. Подробнее: [Выключенные по умолчанию предупреждения компилятора](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Следующий пример приводит к возникновению ошибки C4263:

```
// C4263.cpp
// compile with: /W4
#pragma warning(default:4263)
#pragma warning(default:4264)
class B {
public:
   virtual void func();
};

class D : public B {
   void func(int);   // C4263
};

int main() {
}
```