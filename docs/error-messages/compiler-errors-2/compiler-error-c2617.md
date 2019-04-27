---
title: Ошибка компилятора C2617
ms.date: 11/04/2016
f1_keywords:
- C2617
helpviewer_keywords:
- C2617
ms.assetid: d6a435d2-7d95-4dbf-ad4a-abe4744f63e8
ms.openlocfilehash: 21add86e37d32525b69a02e848444919fe2a79f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208522"
---
# <a name="compiler-error-c2617"></a>Ошибка компилятора C2617

«функция»: несовместимый оператор return

Указанная функция не имеет объявленный тип возвращаемого значения, а предыдущий возвращаемое значение не предоставлено инструкции.

Следующий пример приводит к возникновению ошибки C2617:

```
// C2617.cpp
int i;
func() {   // no return type prototype
   if( i ) return;   // no return value
   else return( 1 );   // C2617 detected on this line
}
```

Возможное решение

```
// C2617b.cpp
// compile with: /c
int i;
int MyF() {
   if (i)
      return 0;
   else
      return (1);
}
```