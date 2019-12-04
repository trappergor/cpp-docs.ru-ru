---
title: Ошибка компилятора C2394
ms.date: 11/04/2016
f1_keywords:
- C2394
helpviewer_keywords:
- C2394
ms.assetid: 653fa9a0-29b3-48aa-bc01-82f98f717a2b
ms.openlocfilehash: 2c8c23939298f5603b59636ede08b65acaa0f22b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744996"
---
# <a name="compiler-error-c2394"></a>Ошибка компилятора C2394

"your_type:: оператор'оп" ": недопустимый CLR или Винртоператор. По крайней мере один параметр должен иметь следующие типы: "не ^", "t ^%", "t ^ &", где T = "your_type"

Оператор в управляемом типе или типе среды выполнения Windows не содержал по крайней мере один параметр, тип которого совпадает с типом значения, возвращаемого оператором.

Следующий пример приводит к возникновению ошибки C2394:

```cpp
// C2394.cpp
// compile with: /clr /c
ref struct Y {
   static Y^ operator -(int i, char c);   // C2394

   // OK
   static Y^ operator -(Y^ hY, char c);
   // or
   static Y^ operator -(int i, Y^& rhY);
};
```
