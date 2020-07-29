---
title: Ошибка компилятора C2562
ms.date: 11/04/2016
f1_keywords:
- C2562
helpviewer_keywords:
- C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
ms.openlocfilehash: 7efc94cc859bbee6db0ce973135c7501fd79ae1d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206943"
---
# <a name="compiler-error-c2562"></a>Ошибка компилятора C2562

"идентификатор": функция "void", возвращающая значение

Функция объявлена как, **`void`** но возвращает значение.

Эта ошибка может быть вызвана неправильным прототипом функции.

Эту ошибку можно исправить, если указать тип возвращаемого значения в объявлении функции.

Следующий пример приводит к возникновению ошибки C2562:

```cpp
// C2562.cpp
// compile with: /c
void testfunc() {
   int i;
   return i;   // C2562 delete the return to resolve
}
```
