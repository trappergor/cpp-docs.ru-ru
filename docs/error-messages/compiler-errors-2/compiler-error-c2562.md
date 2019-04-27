---
title: Ошибка компилятора C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: c665c4ed82fefaf0ee724defb8c205f86fc06dd0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228895"
---
# <a name="compiler-error-c2562"></a>Ошибка компилятора C2562

«Идентификатор»: «void» функция, возвращающая значение

Функция объявлена как `void` , но возвращает значение.

Эта ошибка может быть вызвана неверным прототипом функции.

Чтобы устранить эту ошибку, укажите тип возвращаемого значения в объявлении функции.

Следующий пример приводит к возникновению ошибки C2562:

```
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```