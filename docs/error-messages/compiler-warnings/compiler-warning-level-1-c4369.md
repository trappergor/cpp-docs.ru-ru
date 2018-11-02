---
title: Предупреждение компилятора (уровень 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b374b67fa3319be35490358d7664bcb45bc640db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623960"
---
# <a name="compiler-warning-level-1-c4369"></a>Предупреждение компилятора (уровень 1) C4369

«Перечислитель»: значение перечислителя «значение» нельзя представить в виде «тип», значение — «новое_значение»

Перечислитель полученное значение больше, чем максимальное значение для указанного базового типа.  Это привело к переполнению и компилятор изменил значение перечислителя минимальное возможное значение для типа.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4369.

```
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```