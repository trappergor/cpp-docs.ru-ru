---
title: Ошибка компилятора C2751
ms.date: 11/04/2016
f1_keywords:
- C2751
helpviewer_keywords:
- C2751
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
ms.openlocfilehash: 7b9d8ca4acbbda011cdfa7a467cbb8323dcc7cc5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759598"
---
# <a name="compiler-error-c2751"></a>Ошибка компилятора C2751

"параметр": имя параметра функции не может быть полным

В качестве параметра функции нельзя использовать полное имя.

Следующий пример приводит к возникновению ошибки C2751:

```cpp
// C2751.cpp
namespace std {
   template<typename T>
   class list {};
}

#define list std::list
void f(int &list){}   // C2751
```
