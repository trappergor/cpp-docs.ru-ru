---
title: Ошибка компилятора C3286
ms.date: 11/04/2016
f1_keywords:
- C3286
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
ms.openlocfilehash: 8c09ea34c7dabf2cadecad7c76d766c9496f5a5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461013"
---
# <a name="compiler-error-c3286"></a>Ошибка компилятора C3286

> "*описатель*": у переменной цикла не может иметь любой спецификаторы классов хранения

Класс хранения не может указываться для переменной итерации. Дополнительные сведения см. в разделе [классы хранения (C++)](../../cpp/storage-classes-cpp.md) и [для каждого из них в](../../dotnet/for-each-in.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка c3286: и также показано правильное использование.

```cpp
// C3286.cpp
// compile with: /clr
int main() {
   array<int> ^p = { 1, 2, 3 };
   for each (static int i in p) {}   // C3286
   for each (int j in p) {}   // OK
}
```