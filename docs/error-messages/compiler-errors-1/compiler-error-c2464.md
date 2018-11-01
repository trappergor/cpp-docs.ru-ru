---
title: Ошибка компилятора C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: a00ac997f73175eeab08a0132128e48e8fc58feb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498193"
---
# <a name="compiler-error-c2464"></a>Ошибка компилятора C2464

«Идентификатор»: нельзя использовать «new» для выделения памяти для ссылки

Идентификатор ссылки был выделен с помощью `new` оператор. Ссылки не являются объектами памяти, поэтому `new` не может вернуть указатель на них. Используйте стандартные объявление переменной синтаксис для объявления ссылки.

Следующий пример приводит к возникновению ошибки C2464:

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```