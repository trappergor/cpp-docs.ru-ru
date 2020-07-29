---
title: Ошибка компилятора C2318
ms.date: 11/04/2016
f1_keywords:
- C2318
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
ms.openlocfilehash: 5f608d0407c24bd01ed7b80dbef873dd30662661
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221254"
---
# <a name="compiler-error-c2318"></a>Ошибка компилятора C2318

нет блока try, связанного с этим блоком catch

**`catch`** Обработчик определен, но не предшествует **`try`** блоку.

В следующем примере возникает ошибка C2318:

```cpp
// C2318.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   // no try block
   catch( int ) {}   // C2318
}
```

Возможное решение:

```cpp
// C2318b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try{}
   catch( int ) {}
}
```
