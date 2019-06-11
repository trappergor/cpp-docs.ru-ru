---
title: Ошибка компилятора C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: d48806982bbb6cdda4d29e47f6692e7e3601d6de
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66503216"
---
# <a name="compiler-error-c2362"></a>Ошибка компилятора C2362

> Инициализация "*идентификатор*" пропускается "goto *метка*"

При компиляции с помощью [/Za](../../build/reference/za-ze-disable-language-extensions.md), перехода к метке предотвращает инициализацию идентификатор.

Вы может переходить только после объявления с инициализатором Если объявление содержится в блоке, который не введен, или в том случае, если переменная уже инициализирован.

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