---
title: Ошибка компилятора C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c7dac0abb7d65d3f26522ea1a04577643b7b9eca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212830"
---
# <a name="compiler-error-c2246"></a>Ошибка компилятора C2246

"идентификатор": недопустимый статический элемент данных в локально определенном классе

Объявлен член класса, структуры или объединения с локальной областью видимости **`static`** .

Следующий пример приводит к возникновению ошибки C2246:

```cpp
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```
