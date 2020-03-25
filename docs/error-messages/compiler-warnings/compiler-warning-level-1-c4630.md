---
title: Предупреждение компилятора (уровень 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 414388fc1b9c6a7425d45e2ba92546960cadf404
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199619"
---
# <a name="compiler-warning-level-1-c4630"></a>Предупреждение компилятора (уровень 1) C4630

"символ": спецификатор класса хранения "extern" недопустим для определения члена

Элемент данных или функция-член определяется как `extern`. Элементы не могут быть внешними, хотя все объекты могут. Компилятор игнорирует ключевое слово `extern`. Следующий пример приводит к возникновению ошибки C4630:

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
