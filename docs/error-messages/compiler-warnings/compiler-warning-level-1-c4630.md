---
title: Предупреждение компилятора (уровень 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 3a533afe141a465fb034ba7d90b22a8206bf0910
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230627"
---
# <a name="compiler-warning-level-1-c4630"></a>Предупреждение компилятора (уровень 1) C4630

"символ": спецификатор класса хранения "extern" недопустим для определения члена

Элемент данных или функция-член определяется как **`extern`** . Элементы не могут быть внешними, хотя все объекты могут. Компилятор игнорирует **`extern`** ключевое слово. Следующий пример приводит к возникновению ошибки C4630:

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
