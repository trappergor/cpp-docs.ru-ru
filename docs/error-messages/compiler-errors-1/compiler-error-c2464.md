---
title: Ошибка компилятора C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: b2d2766b11d15bdb666baa207591cc9ff279a280
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225479"
---
# <a name="compiler-error-c2464"></a>Ошибка компилятора C2464

"идентификатор": невозможно использовать "New" для выделения ссылки

Идентификатор ссылки был выделен **`new`** оператором. Ссылки не являются объектами памяти, поэтому **`new`** не могут возвращать указатель на них. Используйте синтаксис объявления стандартной переменной для объявления ссылки.

Следующий пример приводит к возникновению ошибки C2464:

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
