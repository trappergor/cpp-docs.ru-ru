---
title: Ошибка компилятора C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 330932f53627f8ba09e9e089cec7809eeeb6ab1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206080"
---
# <a name="compiler-error-c2362"></a>Ошибка компилятора C2362

> Инициализация "*идентификатор*" пропускается "GoTo *Label*"

При компиляции с помощью [/Za](../../build/reference/za-ze-disable-language-extensions.md)переход к метке предотвращает инициализацию идентификатора.

Можно перейти только к объявлению с инициализатором, если объявление заключено в блок, который не был введен, или если переменная уже была инициализирована.

Следующий пример приводит к возникновению ошибки C2362:

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Возможное решение

```cpp
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
