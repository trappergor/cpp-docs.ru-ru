---
title: Ошибка компилятора C2751
ms.date: 11/04/2016
f1_keywords:
- C2751
helpviewer_keywords:
- C2751
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
ms.openlocfilehash: 14f458725564d39851ae16b5fd2cd5a79f00420d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470802"
---
# <a name="compiler-error-c2751"></a>Ошибка компилятора C2751

«параметр»: имя параметра функции не может быть задан

Полное имя нельзя использовать в качестве параметра функции.

Следующий пример приводит к возникновению ошибки C2751:

```
// C2751.cpp
namespace std {
   template<typename T>
   class list {};
}

#define list std::list
void f(int &list){}   // C2751
```