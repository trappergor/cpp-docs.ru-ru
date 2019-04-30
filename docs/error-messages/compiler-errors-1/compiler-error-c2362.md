---
title: Ошибка компилятора C2362
ms.date: 11/04/2016
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 17656b2a48a3680a9269d3ca300fd4188eda6b84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364328"
---
# <a name="compiler-error-c2362"></a>Ошибка компилятора C2362

Пропуск инициализации «идентификатор», «goto "Метка»

При компиляции с параметром [/Za](../../build/reference/za-ze-disable-language-extensions.md), переходе к метке предотвращает инициализацию идентификатор.

Нельзя перейти назад объявление с помощью инициализатора, только если объявление в блоке, который не выполняется, или переменная уже инициализирован.

При компиляции следующего примера возникнет ошибка C2326:

```
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Возможное решение

```
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```