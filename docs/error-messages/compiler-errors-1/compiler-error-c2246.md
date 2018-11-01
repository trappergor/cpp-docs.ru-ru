---
title: Ошибка компилятора C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c8efb71e0a39c56628fc582421e0f24ceb9b290c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464978"
---
# <a name="compiler-error-c2246"></a>Ошибка компилятора C2246

"идентификатор": недопустимый статический элемент данных в локально определенном классе

Член класса, структуры или объединения с локальной областью объявлен как `static`.

Следующий пример приводит к возникновению ошибки C2246:

```
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```